

## ✅ Exercise 1: Login Toggle

> **Goal:** Display "Welcome, User!" if logged in, else show "Please log in". Add a button to toggle the login state.

### Expected Output:

```
Welcome, User!
[Logout]
```

or:

```
Please log in
[Login]
```

### Hint:

* Use a boolean `isLoggedIn` state.
* Toggle with a button using `onClick`.
* Use **ternary operator** for conditional rendering.

---

## ✅ Exercise 2: Show/Hide Details

> **Goal:** Create a "Show Details" button that toggles showing additional information.

### Expected Output:

```
[Show Details]

-- when clicked --

Here are the extra details you wanted!
[Hide Details]
```

### Hint:

* Use `&&` rendering for the details.
* Change button text conditionally.

---

## ✅ Exercise 3: Conditional Styling with Status

> **Goal:** Render a message with a color depending on a **status variable** (`success`, `error`, `info`).

### Example Output:

If `status = 'success'`:

> "Operation successful!" (green text)

If `status = 'error'`:

> "There was an error!" (red text)

If `status = 'info'`:

> "This is some information." (blue text)

### Hint:

* Use a **switch statement** or ternary chain.
* Apply inline styles conditionally.

---


## ✅ Bonus Exercise: Combine All

Create a **dashboard component** where:

* If **not logged in**, show: `Please log in`
* If **logged in**, show:

  * Welcome message with the username.
  * A "Show Stats" button that toggles showing a **mock stats component**.
  * Status of the server with **conditional styling**.
  * A "Log out" button.

---
