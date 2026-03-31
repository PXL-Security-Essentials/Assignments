# Nmap enumeration
## Setting up the environment
Click the "start container" button and wait 2 minutes. When you get a public IP address use nmap to scan for open ports & services.

## Enumeration
A web server is running on the target machine, but it is not the only service. In real-world penetration testing, services can be exposed on any port — not just the standard ones (80, 443).
Thorough enumeration means scanning all ports and inspecting service banners. Identify the target host provided by this lab, then visit the web interface at http://<target> and read the instructions on the page.

Run an nmap version scan against the target to discover all open ports and services. Connect to each discovered service and retrieve the flag from its banner. You can use nmap output or connect manually using `netcat`:
```
nc <target> <port>
```
