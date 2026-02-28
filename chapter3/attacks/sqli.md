# Basic SQL injection
For months, a rival Minecraft server has been mocking yours. Their players spam your Discord. Their admins brag endlessly about their “untouchable” custom-built control panel. According to them, their infrastructure is rock solid, their authentication flawless, their database secure.

You are not convinced.

One evening, you discover the IP address of their web-based admin panel. It looks ordinary enough: a login form with fields for username and password. No CAPTCHA. Just a clean interface and a bold claim underneath: “Unauthorized access is impossible.”

Your objective is to investigate that claim.

You are given a deliberately vulnerable web application that simulates this rival admin panel. Your mission is to:
- Access the login page hosted at the provided IP address.
- Analyze how the authentication mechanism may be implemented.
- Attempt to bypass the login form using SQL injection techniques.
- If successful, gain access to the admin dashboard.

Once inside, locate the “server control” functionality and simulate wiping the server database.

You must document:
- What inputs you tested and why.
- What behavior the application exhibited.
- The payload that successfully bypassed authentication.
- A technical explanation of why the injection worked.
- How the vulnerability could be fixed properly.