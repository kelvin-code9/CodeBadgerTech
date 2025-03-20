## Finding description and impact

The smart contract is designed to require users to hold the reallocated tokens in their wallet for the minimum required time period before claiming rewards. However, due to a flaw in the contract logic, users can sell, transfer, or move their tokens out of the wallet before the holding period ends and still claim rewards after the holding period ends.

📌 **Reference from Documentation:**  
The official documentation states:  
> *"Nudge monitors participating wallet addresses to ensure that users hold the amount of target tokens reallocated in their wallet for the minimum required time period."*  

This statement is **contradicted** by the bug, as users can sell or transfer tokens and still be eligible for rewards.

### Root Cause:
- The contract checks only the initial reallocation event and does not verify the current  token balance when a user attempts to claim rewards.

### Impact

- This means users can bypass the holding requirement by reallocating, immediately selling or transferring the tokens, and then returning after the period to claim rewards.

- Reward Pool Drain: Attackers can repeatedly participate, dump tokens, and drain rewards with no economic stake.

- The intended mechanism of ensuring long-term token demand and commitment is undermined.

## Proof of Concept

Code Reference
No Token Balance Check in `NudgeCampaign.sol::claimRewards`:
The function validates only the elapsed time, not token ownership.

Add the following test to `NudgeCampaignReallocation.t.sol`
```solidity
function test_UsersDontNeedToHoldTokensToClaimRewards() public {
    uint256 toAmount = 100e18;
    bytes memory data = "";

    // 1. Set up initial balances
    deal(address(targetToken), swapCaller, toAmount);
    vm.prank(swapCaller);
    targetToken.approve(address(campaign), toAmount);

    // 2. Perform reallocation for Alice
    vm.prank(swapCaller);
    campaign.handleReallocation(1, alice, address(targetToken), toAmount, data);

    // Verify Alice received target tokens
    assertEq(targetToken.balanceOf(alice), toAmount, "Alice should have target tokens after reallocation");

    // 3. Alice immediately sells/transfers all target tokens
    vm.prank(alice);
    targetToken.transfer(bob, toAmount);
    assertEq(targetToken.balanceOf(alice), 0, "Alice should have 0 target tokens after transfer");
    assertEq(targetToken.balanceOf(bob), toAmount, "Bob should receive Alice's tokens");

    // 4. Fast-forward past holding period
    vm.warp(block.timestamp + HOLDING_PERIOD + 1);

    // 5. Alice claims rewards despite holding 0 tokens
    uint256 initialRewardBalance = rewardToken.balanceOf(alice);
    uint256[] memory pIDs = new uint256[](1);
    pIDs[0] = 1; // Use the first participation ID

    vm.prank(alice);
    campaign.claimRewards(pIDs);

    // Verify rewards received
    (uint256 expectedRewards,) = campaign.calculateUserRewardsAndFees(campaign.getRewardAmountIncludingFees(toAmount));
    assertEq(
      rewardToken.balanceOf(alice) - initialRewardBalance,
      expectedRewards,
      "Alice should receive full rewards without holding tokens"
    );
  }
```
Result
Test Passes: Alice claims rewards despite transferring all tokens.

## Recommended mitigation steps
To fix this vulnerability, the contract should:  

1. **Track Wallet Balance at Claim Time**  
   - When a user tries to claim rewards, the contract should **verify that they still hold the required amount of tokens**.  
   - This can be done using a balance check via the token contract (`balanceOf(userAddress)`).  

2. **Implement a Continuous Balance Monitoring System**  
   - Instead of only checking balance at the start, integrate a method to track changes in token holdings over time.    

3. **Penalty or Auto-Disqualification for Early Transfers**  
   - If a user moves tokens before the required time, they should automatically be **disqualified** from claiming rewards.  

---
