# manage-authorization-linux-lab
Linux File Permissions &amp; Authorization Lab - Google Cybersecurity Profesional Certificate
Linux File Permissions in Linux – Manage Authorization Lab
Project Description

As part of the Google Cybersecurity Professional Certificate, I completed a hands-on lab titled “Manage Authorization.”

In this activity, I reviewed and updated file and directory permissions within the projects directory to ensure they reflected the appropriate level of access. Checking and updating these permissions reinforced proper access control and system security principles.

Check File and Directory Details

To determine the existing permissions set for the directory and its contents, I used:

ls -la
Purpose of the Command:

Lists all files and directories (including hidden files)

Displays detailed file information

Shows permissions, ownership, and file types

Output Observations:

One directory named drafts

One hidden file named .project_x.txt

Five additional project files

A 10-character permission string for each file

Understanding the Permission String

Each file has a 10-character string that identifies:

File type

User permissions

Group permissions

Other permissions

Format Breakdown

Example:

-rw-rw-r--
Explanation:

1st character

d = directory

- = regular file

2nd–4th characters (User)

r = read

w = write

x = execute

- = permission not granted

5th–7th characters (Group)

Same permission structure as user

8th–10th characters (Other)

Permissions for all other users on the system

Example Interpretation

For:

-rw-rw-r--

It is a regular file

User has read and write

Group has read and write

Other have read only

No one has execute permission

Change File Permissions
Scenario:

Other should not have write access to any files.

After reviewing permissions, I determined that project_k.txt required modification.

Command Used:
chmod o-w project_k.txt
Explanation:

o-w removes write permission from other

The file name specifies the target file

After making the change, I confirmed the update using:

ls -la
Change File Permissions on a Hidden File
Scenario:

The file .project_x.txt was archived and required restricted permissions:

No write access for anyone

User and group should have read access

Since the file begins with a period (.), it is a hidden file.

Commands Used:
chmod u-w .project_x.txt
chmod g-w .project_x.txt
chmod g+r .project_x.txt
Explanation:

u-w → removes write permission from the user

g-w → removes write permission from the group

g+r → adds read permission to the group

Change Directory Permissions
Scenario:

Only the researcher2 user should have access to the drafts directory and its contents.

No other users or groups were permitted to execute files within that directory.

Command Used:
chmod g-x drafts
Explanation:

g-x removes execute permission from the group

This restricts group members from accessing directory contents

Permissions were verified using:

ls -la
Summary

In this lab activity, I:

Reviewed file and directory permissions

Interpreted Linux permission strings

Modified file access using chmod

Verified changes using ls -la

Applied secure access control principles

This lab strengthened my understanding of:

Linux file systems

Authorization management

Access control mechanisms

Secure system configuration

Completed as part of the Google Cybersecurity Professional Certificate
