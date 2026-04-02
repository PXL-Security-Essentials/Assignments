# Lab: Chrome DevTools Enumeration
Not everything a web application exposes is visible on screen. Developers frequently leave sensitive information in places that are only accessible through careful inspection:

- HTML source hidden fields that control access level
- JavaScript files with hardcoded configuration or tokens
- Cookies that contain encoded session data
- Background API requests that never surface in the UI

This lab gives you hands-on practice discovering each of these using Chrome DevTools (`F12`).

## Getting Started

Navigate to the challenge IP after pressing the start challenge button. You will land on the **Veldt Corp Internal Portal** login page.

## Tasks

### Flag 1 — Elements Tab

1. Open DevTools (`F12`) and go to the **Elements** tab.
2. Inspect the login form.
3. Find the hidden input field that controls the access level.
4. Change its value so that you log in as an administrator.
5. Submit the form. The flag will be displayed on the page.

> **Tip:** Right-click the Sign In button and choose *Inspect* to quickly locate the surrounding form fields.

---

### Flag 2 — Sources Tab

1. After logging in, navigate to the **dashboard**.
2. Open DevTools and go to the **Sources** tab.
3. Browse the JavaScript files loaded by the page.
4. Look for a configuration object that a developer forgot to remove before deployment.
5. The flag is a value inside that object.

> **Tip:** Try `top → (no domain) → js/` in the Sources panel file tree.

---

### Flag 3 — Application Tab

1. On the dashboard, open the **Application** tab in DevTools.
2. Expand **Cookies** in the left-hand sidebar and select the current site.
3. Find the session cookie set after your admin login.
4. The cookie value is Base64-encoded. Decode it to reveal the flag.

> **Tip:** You can decode Base64 in the DevTools Console: `atob('<cookie value here>')`

---

### Flag 4 — Network Tab

1. Open the **Network** tab in DevTools *before* loading or refreshing the dashboard.
2. Reload the page and observe all requests that fire.
3. Find the background request to an internal diagnostics endpoint.
4. Inspect the JSON response body — the flag is inside it.

> **Tip:** Filter by **Fetch/XHR** in the Network tab to hide noise.

---

## Deliverables

Submit all four flags in the format `PXL{...}`.

| # | DevTools Tab | Flag |
|---|---|---|
| 1 | Elements | `PXL{...}` |
| 2 | Sources | `PXL{...}` |
| 3 | Application | `PXL{...}` |
| 4 | Network | `PXL{...}` |
