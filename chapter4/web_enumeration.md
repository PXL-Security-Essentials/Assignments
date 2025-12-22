# Setting up the environment
Click the "start container" button and wait 2 minutes. When you get a public IP address use nmap to scan for open ports & services.
# Enumration
You'll notice a webserver running. Try answering the following questions:
- What ports are open on this server?
- What type of webserver is running this port? What is the version number?
- Are there any CVEs linked to this webserver? Describe these.

Use any popular tool to scan for known files/folders on the webserver. Then answer the following questions:

- What extension does the index page on the web server have?
- How can you use dirb to search for specific extensions?
- What (hidden) files did you find?
- Which flags did you find in which files?

Make sure you validate any flags you've found below.