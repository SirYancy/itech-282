---
layout: default
title: Chapter 13 - Users, Groups, and Permissions
nav_order: 13
permalink: /chapter-13
mathjax: true
---

Chapter 13 - Users, Groups, and Permissions
===========================================

How do you protect all of your information from other users?

A combination of user accounts, groups, and NTFS permissions facilitate a robust security system for Windows.

## Authentication

* A *user account* is a combination of a user name and a password stored in a database.
* This grants the user access to the system.
* User accounts are not just for humans.
* Everything that runs on the computer is attached to an account.
* The SYSTEM account is used by Windows to run programs
* Two mechanisms are at play:
    * *Authentication* is identification and access. This is usually handled by a password-protected user account
    * *Authorization* is the mechaism that takes over after authentication. It defines what resources an authenticated user has access to.
* Every resource (files, etc) on NTFS filesystem is controlled by user accounts. It's built into the filesystem.

### User Accounts

* Every account has a user name and a password. A user name is a text string that identifies a user account assigned to a system.
* It can be a name or an email address.
* The password is likewise a unique key known only to the user and the system (in theory).
* These are both encrypted in the system.
* The encrypted database stores records called *local user accounts*.
* This is different in different systems (considering always-on Internet).
* ChromeOS requires a google account.
* Linux relies exclusively on local accounts.
* Windows and MacOS split the difference.
* You can use a local account, or a global Microsoft or Apple account. These synchronize some aspects of your experience. Such as desktop backgrounds, etc.
* Creating an account adds a user to the database and adds a set of folders to the computer. Documents, Desktop, Pictures, etc
* Only the user associated with the account can access those folders.

### Passwords

* Passwords are important. Remember the usual wisdom of protecting passwords.
* Even an account with limited access that is compromised is still a security breach.
* Let's talk about the CompTIA recommendations vs NIST recommendations.
* Windows requires a password hint (why is this bad?)

### Groups

* A group is a container full of users.
* It defines the capabilities of the users in the container
* An efficient way of managing many users
* This is slightly obscured in Windows Home, for example
* Groups have two advantages:
    * You can assign levels of access for a file or folder to a group. When someone is hired, you simply add them to a group and boom.
    * Windows provides several built-in groups with access levels pre-determined.
* These are the groups you should know about:
    * **Administrators** have complete administrator privileges. 
    * **Power Users** are almost as powerful, but cannot install new devices or access users' files or folders.
    * **Users** cannot edit the registry or access system files. They can create groups, but can only manage the ones they create.
    * **Guests** gives someone who does not have an account to log on using the guest account. Maybe you'll have it available at a party so someone can change the tunes or at a library for internet access or whatever. Usually, it's disabled.

### Standard User and Elevated Privileges

* Typical: single primary user account--a standard user--and a local admin account for doing important things (installing apps, etc)
* If you want to do something big, you can "run as administrator" certain programs. A popup will *always* warn you when you're elevating privileges for some app or process.

### Configuring Users and Groups

* Local Users and Groups applet. `lusrmgr.msc`
* Windows 10 Home does not have this.
* Let's explore this applet
* There are differences between 7/8/8.1/10. Also, there's a lot of legacy baggage that comes with Windows 10.

### Authorization and NTFS

* Every file and folder in NTFS has a list of users and groups.
* It specifies who can access the file/folder and *at what level*.
* These are specified by *NTFS permissions*.
* There's a lot of detail here. So we can look at these permissions now.
* 1002 only wants you to know about a few things:
    * **Ownership** when you create a file you are the *owner*.
    * **Take Ownership** anyone with this permission can take a file or folder. Administrator accounts obviously have this permission. Even if you block the admin, they can *take* ownership and *then* access the file.
    * **Change permission** this allows you to give or take away from users or groups on a file
    * **Folder permissions** a set of permissions on folders. ie "list folder contents"
    * **File permissions** a set of file-level permissions ie "read and execute"
* See standard permissions in text (p 546)

### Inheritance

* Basic rule: any file placed in a folder receive that folder's permissions
* This is turned on by default (but can be disabled, which can create all sorts of interesting problems). Though there are times when it can be useful.

### Permission Propagation

* What happens when files are moved in different situations?
* Look at these carefully in the text. (p 549)
