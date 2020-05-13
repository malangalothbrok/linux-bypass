
# WHAT IS SUDO?

Sudo, abbreviated for Super User Do, is a program for UNIX and Linux systems that gives the user the permissions needed to run commands and scripts as the root of the system and logs all the commands and arguments. A sudo system administrator can:

- Give permissions for users to run root commands of the system operation
- Control the commands a user can use of each host
- See the commands used by the users via a log
- Control the time duration given for each user to enter commands after logging through the use of timestamp files

# SUDORE FILE

This is a file located at /etc/sudoers which controls the sudo command privileges within users, which includes elevated privileges. The best and safest way to edit this is by using the visudo command. This command allows you to edit and save the file by using vi editor. This will also put a filelock on the file to prevent other users from editing it. Once editing is done, it will parse the file for simple errors [2]

## How to setup attack

1. Download Ubuntu 16.4 from a secure website, most commonly used is oxboxes.org [3]
2. Install virtual box from the website
3. Open virtual box and add a new machine
4. Give a name to your virtual machine
5. Set the file path to the image
6. Give type as linux
7. Set version as your downloaded file whether 64bit or 32bit
8. Set RAM size and create

## Vulnerability details

- Release date: 14th October 2019
- CVE ID: CVE-2019-14287
- Affected Versions: Versions prior to \&lt;= 1.8.28
- [**https://www.sudo.ws/alerts/minus\_1\_uid.html**](https://www.sudo.ws/alerts/minus_1_uid.html)

# Brief description of vulnerability

Even though user permissions in the sudoer file mentions that it explicitly prevents users running commands as root, the security bypass vulnerability allows the users with Linux systems to execute commands as root.

A user which as ALL permissions in the Runas specifications can execute these commands on any or all the users of the system.

This vulnerability allows the users to specify their user ID as -1 or the unsigned equivalent of -1: 4294967295 and this allows the users to run commands and tools as root.

sudo -u#-1 /usr/bin/id or the unsigned equivalent of -1 sudo -u#4294967295 /usr/bin/id

