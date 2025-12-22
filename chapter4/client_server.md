# Setting up the environment
Click the "start container" button and wait 2 minutes. When you get a public IP address use nmap to scan for open ports & services. You'll notice a webserver running.

# Enumeration
Use Nmap to enumerate this port and determine what service or runtime is running on it. This port hosts a 3-tier web application. A 3-tier application is a modular client-server architecture consisting of a presentation layer (frontend), an application layer (backend API), and a data layer (database). Investigate this service and answer the following questions:

1. What runtime is being used on this port? Provide some information about this runtime environment.
2. You'll notice that the application uses Express.js. Provide a general description of Express.js's goals.
3. What are some of the most commonly used frameworks for backend development?
4. What are some of the most commonly used frameworks for frontend development?

# Manipulating network traffic
While enumerating the service, you will encounter a login page. In this instance, you are provided with login credentials:
```
Username: john
Password: secret
```
Explore the application and its features. Use your browser's developer tools our burp suite to assist in the investigation. The goal of this challenge is to log in as another user. Answer the following questions:
- Who is the other active user in the application?
- Find a way to log in as the alternative user without using brute-force tools. Describe the method used.
- Within the OWASP Top 10, which category does this attack fall under? Justify your answer.

Make sure you validate the flags using the flag validator tool.