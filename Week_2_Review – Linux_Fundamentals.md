# Week 2 Review – Linux Fundamentals
# Goal

Review all topics from Week 2 of TryHackMe:

Linux filesystem, users, permissions
Basic commands (ls, cd, mkdir)
File management (rm, chmod)
Text processing (cat, grep)
SSH basics and keys
Users & groups

Consolidate notes, diagrams, and examples into a single GitHub repository for reference.

# Topics Reviewed
## Linux Filesystem, Users & Permissions
Filesystem hierarchy (/home, /etc, /bin, /var)
File ownership and permissions (r, w, x)
Viewing permissions: ls -l
Changing permissions: chmod

Example:

mkdir test_folder
cd test_folder
touch file.txt
chmod 755 file.txt
ls -l
## Basic Commands (ls, cd, mkdir)
Navigating directories: cd, pwd
Listing files: ls
Creating directories and files: mkdir, touch

Example:

mkdir my_project
cd my_project
mkdir files
touch notes.txt
ls -l
## File Management (rm, chmod)
Consolidating notes and diagrams improves retention and reference for labs and pentesting
## File Management (rm, chmod)
Remove files or directories: rm
Modify permissions: chmod

Example:

rm notes.txt
chmod 600 file.txt
ls -l
## Text Processing (cat, grep)
View file content: cat file.txt
Search inside files: grep "keyword" file.txt

Example:

cat notes.txt
grep "Linux" notes.txt
5️## SSH Basics & Keys
Connect to remote VM: ssh user@ip
Use private key: ssh -i key.pem user@ip
Fix permissions for private key: chmod 600 key.pem

Example:

ssh -i id_rsa admin@10.10.10.10
## Users & Groups
Create users: adduser username
Create groups: groupadd groupname
Add user to group: usermod -aG groupname username
Check user info: id username, groups username

Example:

sudo adduser hacker
sudo groupadd pentest
sudo usermod -aG pentest hacker
id hacker
# Notes & Diagrams
Notes:
Linux filesystem: root / → organizes all directories
Permissions: rwx for owner, group, others
SSH keys: private key must be chmod 600
User groups determine access level
Diagrams:

Filesystem Hierarchy:

/
├── bin
├── etc
├── home
│   ├── user1
│   └── user2
├── tmp
└── var

Permissions Example:

-rwxr-xr--
Owner: read, write, execute
Group: read, execute
Others: read

SSH Key Flow:

Local PC --SSH--> Remote VM
         (private key)
# Key Takeaways
Week 2 focused on Linux basics, file management, text processing, SSH, and user/group management
Understanding permissions and groups is critical for security
SSH keys allow secure remote access
Consolidating notes and diagrams improves retention and reference for labs and pentesting








