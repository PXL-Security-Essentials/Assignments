# Setting up the environment
Click the "start container" button and wait 2 minutes. When you get a public IP address use nmap to scan for open ports & services.

# Filesharing
For this task you will be enumerating a SAMBA (SMB) share. Try enumerating using the questions below:

- What is SAMBA? What is its purpose? What port(s) does it run on?
- What are some alternatives for the SMB protocol?
- Use the SMBclient tool to enumerate this service. What shares are available on this service?
- Only one share is relevant to this assignment and accessible (Tip: Not the IPC$ one). Find a way to connect to this share. Pay close attention to version numbers and options. Hint: look into cifs shares on linux.
- What files are located on the share? Explore these files! Describe your methodology.
- How did you crack the password-protected file? What did you find inside?

Make sure you validate any flags you've found below.
