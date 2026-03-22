#Users & Groups – TryHackMe
##Goal

To understand how Linux users and groups work, and how to create users and assign them to groups for proper access control.

##Topics Covered
Linux users and accounts
Linux groups and permissions
Creating users
Assigning users to groups
Viewing user and group information
##Commands Used
adduser – create a new user
groupadd – create a new group
usermod – modify a user (add to group)
groups – display user groups
id – show user and group IDs
whoami – display current user
##Creating a User
sudo adduser user1
##Creating a Group
sudo groupadd devs
##Adding User to a Group
sudo usermod -aG devs user1
##Checking User Information
id user1
groups user1
##Example
sudo adduser hacker
sudo groupadd pentest

sudo usermod -aG pentest hacker

id hacker
Output
uid=1001(hacker) gid=1001(hacker) groups=1001(hacker),1002(pentest)
##Practice
Created a new user (hacker)
Created a group (pentest)
Assigned the user to the group
Verified group membership
##What I Learned
How to create and manage users in Linux
How groups control access and permissions
How to assign users to groups
How to verify user roles and privileges
##Security Insight

Misconfigured groups (e.g. adding users to the sudo group) can lead to privilege escalation and unauthorized access.

##Platform

Practice completed on TryHackMe – Users & Groups

##Notes
Always check your privileges:
whoami
id
groups
Users in privileged groups (like sudo) may gain elevated access.
