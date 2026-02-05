# Setting up the environment

# Remote code execution
You have access to a website that allows users to check whether other websites are down or if the issue is only on their own device. However, there may be more to this functionality than meets the eye. Explore the website's functionality and identify the vulnerability that allows you to execute remote commands on the server.

Answer the following questions:

- What is the impact of this exploit? Describe the potential consequences of a successful RCE attack on this application.
- Analyze the source code and pinpoint the exact location of the vulnerability. What causes it?
- What security measures could be implemented to prevent this vulnerability?
- Search for a hidden flag somewhere in the server's files.

# Remote shell
Use the [pentestmonkey's cheatsheet](https://pentestmonkey.net/cheat-sheet/shells/reverse-shell-cheat-sheet) for reverse shells to craft a payload that establishes a reverse shell to your attack machine. You will have to use netcat on your attack box to access the shell.

Answer the following questions:

- Which user are you logged in as? Why?
- What are your permissions? What commands can you run?
- What other users are present on the system?

# Elevating privileges
System admins got sloppy and allowed the `www-data` user to run some commands with sudo privileges. Answer the following questions:
- What command can you run using the sudo command? How did you find out?
- Try to look for options to abuse this command. Is there any way to run other commands through this command?
- Abuse the knowledge above to read the contents of the file `/root/quote.txt`?


Make sure you validate any flags you've found below.
