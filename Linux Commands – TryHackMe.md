Linux Commands – TryHackMe
Goal

To understand how to manage files by deleting them and modifying their permissions using rm and chmod.

Topics Covered

Removing files and directories

Changing file permissions

Understanding Linux permission system

Commands I Used

rm – remove files or directories

chmod – change file permissions

Example
mkdir test_env
cd test_env

touch file1.txt
touch file2.txt

ls                     # list files

chmod 755 file1.txt    # change permissions
ls -l                  # check permissions

rm file2.txt           # delete file
ls                     # verify deletion
Practice Task

I created files, modified permissions, and deleted one of them:

test_env/
├── file1.txt
└── file2.txt

After changes:

test_env/
└── file1.txt
What I Learned

How to delete files using rm

How to modify permissions using chmod

How permissions affect file access

Platform

Practice completed on TryHackMe – Linux Commands
