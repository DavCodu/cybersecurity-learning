#Linux Fundamentals 1 – TryHackMe
#Goal

To understand the Linux filesystem structure, how users and permissions work, and to practice basic commands used for navigation and file management.

#Topics Covered

Linux filesystem structure

File and directory navigation

Linux users and groups

File permissions

#Commands I Used

ls – list files and directories

cd – change directory

pwd – show current working directory

mkdir – create a new directory

touch – create an empty file

cp – copy files or directories

mv – move or rename files

rm – remove files or directories

whoami – show current user

id – show user and group information

chmod – change file permissions

chown – change file ownership

#Filesystem Basics

In Linux everything is organized starting from the root directory:

/

##Important directories:

/home – user home directories

/etc – configuration files

/bin – essential system binaries

/var – logs and variable data

/tmp – temporary files

##Permissions Explained

Linux permissions are divided into:

Owner
Group
Others

##Permission types:

r – read
w – write
x – execute

##Example permission:

-rwxr-xr--

##Meaning:

Owner: read, write, execute
Group: read, execute

##Others: read

##Example
mkdir practice_folder      # create a directory
cd practice_folder         # enter the directory
touch file1.txt            # create a file
ls -l                      # list files with permissions
chmod 755 file1.txt        # change permissions
whoami                     # show current user
id                         # show user and group information

#What I Learned

How Linux organizes files using the filesystem hierarchy
How to navigate between directories using cd
How users and groups work in Linux
How to read and change file permissions using chmod

#Platform

Practice completed on TryHackMe – Linux Fundamentals 1
