#SSH & Keys – TryHackMe
##Goal

To understand how SSH works, how to connect to remote machines, and how SSH keys are used for authentication.

##Topics Covered
SSH remote access
Password authentication
SSH key authentication
File permissions for SSH keys
Basic privilege escalation using SSH keys
##Commands I Used
ssh – connect to a remote machine
ssh -i – connect using a private key
chmod – change file permissions
ls – list files
find – search for files
grep – search for text inside files
##Connecting via SSH

##Basic connection:

ssh user@ip_address

##Using a private key:

ssh -i key.pem user@ip_address
Fixing Key Permissions

SSH requires strict permissions for private keys:

chmod 600 key.pem
Finding SSH Keys

##Searching for private keys on the system:

find / -name "id_rsa" 2>/dev/null

##Searching for key content:

grep -r "PRIVATE KEY" / 2>/dev/null
Example Scenario
Connected to the target machine:
ssh lowuser@target
Searched for SSH keys:
find /home -name "id_rsa" 2>/dev/null
Found a key:
/home/admin/.ssh/id_rsa
Used the key to switch user:
ssh -i id_rsa admin@localhost
What I Learned
How to connect to remote systems using SSH
The difference between password and key authentication
How to locate sensitive files like SSH private keys
How improper permissions can lead to security issues
How SSH keys can be used for privilege escalation
Security Note

Exposed SSH private keys or incorrect permissions (e.g. 777) can lead to unauthorized access and privilege escalation.

##Platform

Practice completed on TryHackMe – SSH & Keys
