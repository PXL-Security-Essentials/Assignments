# Setting up the environment
Click the "start container" button and wait 2 minutes. When you get a public IP address use nmap to scan for open ports & services. You'll notice a webserver running.

# Enumeration & bruteforcing
You'll find a custom web application running on the webserver. Your goal is to enumerate the web application using the questions & tools below:
- What is the purpose of Apache?
- Which programming environment was used to develop the application that is being hosted on the apache webserver?
- As you investigate the login page, what error messages are displayed when attempting to log in?
- Identify a tool capable of brute-forcing a login form within a web application. What tool(s) did you discover? Hint: there may be tools already integrated into your attack box.
- Determine the user associated with the login form (manually or automatically).
- Utilize a tool to bruteforce the password for this user. Provide a description of the executed and build command(s) and the methodology used? Hint: Use the password list found here.
- To which topic within the OWASP top 10 can this attack be attributed? Justify your answer.
- Define "parameter tampering" and offer a brief explanation in your own words.
- Apply parameter tampering within the lab environment and detail your methodology.
Find the last flag within this lab and describe where you found the flag and how this technologie is relevant to the application. Hint: how is login state maintained within web applications?

Make sure you validated the flags you find during this challenge below.