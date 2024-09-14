---
title: "History and Introduction about : Linux"
datePublished: Thu May 18 2023 20:51:42 GMT+0000 (Coordinated Universal Time)
cuid: clhtlxkd30cmxssnv4d6s8fhk
slug: history-and-introduction-about-linux
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1719243053201/468aa7e4-1bf1-4c1a-863b-5eeda8c63b16.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1719243065744/c613691b-c8a2-47d5-8bdb-4c64e1797c7e.png
tags: linux, kernel, linux-for-beginners, linux-basics

---

Linux is a community of open-source Unix-like operating systems that are based on the [**Linux Kernel**](https://www.geeksforgeeks.org/the-linux-kernel/). It was initially released by **Linus Torvalds** on September 17, 1991. It is a free and open-source operating system and the source code can be modified and distributed to anyone commercially or non-commercially under the GNU General Public License.   
Initially, Linux was created for personal computers and gradually it was used in other machines like servers, mainframe computers, supercomputers, etc. Linux went on to become, arguably, the biggest success story of the **free software movement**, proving that open source could lead to the creation of software as powerful as any sold by a corporation.

## **UNIX vs LINUX**

Unix is called the mother of operating systems which laid out the foundation for Linux. Unix is designed mainly for mainframes and is in enterprises and universities. While Linux is fast becoming a household name for computer users, developers and server environments. You may have to pay for Unix kernel while Linux is free.

But the commands used on both operating systems are usually the same. There is not much difference between UNIX and LINUX. Though they might seem different, at the core, they are essentially the same. Since Linux is a clone of UNIX. So learning once. Learning one is the same as learning another.

Unix Family tree

### Linux Distribution

[1 Ubuntu](https://www.stackscale.com/blog/popular-linux-distributions/#Ubuntu)

[**Ubuntu**](https://www.stackscale.com/blog/ubuntu/) is a Linux distribution based on Debian. It is developed by Canonical and a community of developers. It has 3 official editions: *Desktop*, *Server* and *Core*, which can either run on a computer or on a VM. More than 34% of the websites using Linux use Ubuntu, [according to W3Techs data](https://w3techs.com/technologies/details/os-linux). Its growth since 2010 has been amazing. It is also a popular distribution among cloud computing projects.

[2 Debian](https://www.stackscale.com/blog/popular-linux-distributions/#Debian)

[**Debian**](https://www.debian.org/index.en.html) is an open-source operating system. This distribution was first announced by Ian Murdock in 1993 as the “Debian Linux Release”. The Debian Project is a community of developers and users that maintain the GNU OS based on open source software. Currently, Debian systems use the Linux kernel or the FreeBSD kernel. However, they are also working on providing Debian for other kernels. Primarily, GNU Hurd.

[3 CentOS Linux](https://www.stackscale.com/blog/popular-linux-distributions/#CentOS_Linux)

**CentOS** Linux: Stable, secure, open-source OS based on Red Hat Enterprise Linux, ideal for server deployments, offering extensive software packages and long-term support.

[4 Red Hat Enterprise Linux (RHEL)](https://www.stackscale.com/blog/popular-linux-distributions/#Red_Hat_Enterprise_Linux_RHEL)

**Red HatEnterprise Linux (RHEL)** is a leading enterprise-grade operating system known for its stability, security, and support. It offers a robust platform for businesses, providing advanced features, scalability, and reliability. RHEL is widely used across industries and is backed by Red Hat's extensive ecosystem, making it a trusted choice for mission-critical applications and infrastructure.

[5.Fedora](https://www.stackscale.com/blog/popular-linux-distributions/#Fedora)

**Fedora** is a cutting-edge Linux distribution sponsored by Red Hat, known for its focus on innovation and community-driven development. It offers the latest software packages and features, including a user-friendly desktop environment. Fedora serves as a platform for both desktop and server use cases, providing a balance between stability and modernity.

6.[OpenSUSE](https://www.stackscale.com/blog/popular-linux-distributions/#OpenSUSE)

**OpenSUSE** is a robust and user-friendly Linux distribution that emphasizes stability and ease of use. With its flexible package management system and extensive software repository, openSUSE is suitable for both desktop and server environments, catering to a wide range of user needs.

[7.Linux Mint](https://www.stackscale.com/blog/popular-linux-distributions/#Linux_Mint)

**Linux Mint** is a user-friendly and elegant Linux distribution based on Ubuntu. It offers a familiar desktop environment, a wide range of software applications, and a focus on simplicity and usability.

### Architecture of Linux

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684442414217/470eb7cd-c063-41f1-b52d-ad1fcb3faa1d.jpeg align="center")

1. **Kernel:** Kernel is the core of the Linux-based operating system. It virtualizes the common hardware resources of the computer to provide each process with its virtual resources. This makes the process seem as if it is the sole process running on the machine. The kernel is also responsible for preventing and mitigating conflicts between different processes. Different types of the kernel are:
    
    Monolithic Kernel
    
    Hybrid kernels
    
    Exo kernels
    
    Micro kernels
    
2. **System Library: SL** is the special type of function that are used to implement the functionality of the operating system.
    
3. **Shell:** It is an interface to the kernel which hides the complexity of the kernel’s functions from the users. It takes commands from the user and executes the kernel’s functions.
    
4. **Hardware Layer:** This layer consists all peripheral devices like RAM/ HDD/ CPU etc.
    
5. **System Utility:** It provides the functionalities of an operating system to the user.
    

[**Linux File Hierarchy Structure**](https://www.geeksforgeeks.org/linux-file-hierarchy-structure/)

In Linux/Unix operating system everything is a file even directories are files, files are files, and devices like mouse, keyboard, printer, etc are also files. Here we are going to see the Directory Structure in Linux.

### **Types** of files in the Linux system.

1. **General Files** – It is also called ordinary files. It may be an image, video, program, or simple text file. These types of files can be in ASCII or Binary format. It is the most commonly used file in the Linux system.
    
2. **Directory Files** – These types of files are a warehouse for other file types. It may be a directory file within a directory (subdirectory).
    

We know that in a Windows-like operating system, files are stored in different folders on different data drives like C: D: E: whereas in the Linux/Unix operating system files are stored in a tree-like structure starting with the root directory as shown in the below diagram.

The base of the Linux/Unix file system hierarchy begins at the root and everything starts with the root directory.

### **These are the common top-level directories associated with the root directory:**

**/bin** – binary or executable programs.

**/etc** – system configuration files.

**/home** – home directory. It is the default current directory.

**/opt** – optional or third-party software.

**/tmp** – temporary space, typically cleared on reboot.

**/usr** – User-related programs.

**/var** – log files.

### Some other directories in the Linux system:

**/boot-** It contains all the boot-related information files and folders such as conf, grub, etc.

**/dev –** It is the location of the device files such as dev/sda1, dev/sda2, etc.

**/lib –** It contains kernel modules and a shared library.

**/lost+found –** It is used to find recovered bits of corrupted files.

**/media –** It contains subdirectories where removal media devices are inserted.

**/mnt –** It contains temporary mount directories for mounting the file system.

**/proc** – It is a virtual and pseudo-file system to contains info about the running processes with a specific process ID or PID.

**/run –** It stores volatile runtime data.

**/sbin –** binary executable programs for an administrator.

**/srv –** It contains server-specific and server-related files.

**/sys –** It is a virtual filesystem for modern Linux distributions to store and allows modification of the devices connected to the system.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1684565667988/f8a592ec-797f-4315-8b1c-70ac39e0839f.jpeg align="center")

## **Terminal/Shell Description**

**Descriptions of Shell :**

Shell is a user interface that allows users to interact with an operating system. It provides a command-line interface (CLI) or a graphical user interface (GUI) through which users can execute commands, and manage files and directories. A shell acts as a medium between the user and the operating system, clarifying user commands and executing them by calling/arranging the appropriate system programs. It serves as a command processor, taking input from the user and providing output from the operating system.

**Advantages of Shell :**

Automation and scripting capabilities save time and streamline workflows.

Flexibility and customization options allow users to tailor their working environment.

Direct access to system commands and utilities enables efficient system control.

Access to powerful command-line tools and utilities with advanced functionality.

Remote access capabilities facilitate managing systems over networks.

Reproducibility and version control ensure consistent and trackable changes.

Enhances understanding of the operating system and promotes skill development.

Particularly valuable for software developers, system administrators, and technical professionals.

## **Various Types Of Shell.**

There are various types of shells available, with different features and capabilities.

Some popular examples include:

**Bourne shell (sh):** The original Unix shell, which has been the foundation for many other shells.

**Bourne-Again shell (bash):** A widely used shell that is compatible with the Bourne shell but includes additional features.

**C shell (csh):** A shell that provides a syntax and features inspired by the C programming language.

**Korn shell (ksh):** A shell that combines features from the Bourne shell and the C shell, offering powerful scripting capabilities.

**PowerShell:** A shell developed by Microsoft for Windows operating systems, with a focus on automation and system administration tasks.

Shells allow users to control and interact with the underlying operating system efficiently, providing a flexible and powerful means of managing a computer system.

### **What is #!/bin/bash?**

The shebang line, starting with `#!`, is used to specify the interpreter or shell to be used for executing the script. `#!/bin/bash` specifies the Bash shell as the interpreter, while `#!/bin/sh` refers to the system's default shell.

Bash is an enhanced version of the Bourne shell (`/bin/sh`). It provides additional features and capabilities that make it a popular choice for scripting in Linux. Bash is backwards-compatible with the Bourne shell, meaning scripts written for `/bin/sh` will generally work with Bash as well.

However, it's worth noting that some advanced features specific to Bash may not be available in the basic `/bin/sh` shell. If your script relies on Bash-specific features, it's safer to use `#!/bin/bash` to ensure compatibility and avoid any potential issues.

### **Commands Line**

**Definition of command line Interface & types of CLI**

The command line in Linux is a text-based interface that allows users to interact with the operating system by entering commands. Here are key points about the Linux command line:

1. **Terminal:** The command line is accessed through a terminal emulator, providing a text-based environment for executing commands.
    
2. **Shell:** Linux uses various shell programs, such as Bash, as the command line interpreter, which processes commands and executes them.
    
3. **Command syntax:** Commands in Linux typically consist of a command name followed by options, arguments, and flags, allowing users to perform specific tasks and operations.
    
4. **File system navigation:** Users can navigate and manipulate the file system by using commands like `cd`, `ls`, `mkdir`, and `rm` to change directories, list files, create directories, and remove files, respectively.
    
5. **File operations:** Commands like `cp`, `mv`, and `cat` is used for copying, moving, and displaying the contents of files.
    
6. **Process management:** Linux commands such as `ps`, `kill`, and `top` help users manage processes, including listing running processes, terminating them, and monitoring system resource usage.
    
7. **System administration:** The Linux command line provides powerful tools for system administration tasks, including managing users, configuring network settings, installing software packages, and more.
    
8. **Automation and scripting:** The command line allows users to automate tasks and create scripts using scripting languages like Bash, enabling efficient and repeatable operations.
    
9. **Command history and shortcuts:** Users can access command history and use keyboard shortcuts to enhance productivity, saving time and effort.
    
10. **Remote access and administration:** The Linux command line supports remote access and administration via secure protocols like SSH, enabling users to manage remote systems from a command line interface.
    

Overall, the Linux command line provides a versatile and efficient environment for performing a wide range of tasks, from basic file operations to advanced system administration and automation.

### **Commands & their uses in LINUX**

1. Top 50 basic commands in Linux.
    
    1. `ls`: List files and directories in the current directory.
        
    2. `cd`: Change directory.
        
    3. `pwd`: Print the current working directory.
        
    4. `mkdir`: Create a new directory.
        
    5. `rm`: Remove files or directories.
        
    6. `cp`: Copy files and directories.
        
    7. `mv`: Move or rename files and directories.
        
    8. `cat`: Display the contents of a file.
        
    9. `touch`: Create an empty file or update the timestamp of an existing file.
        
    10. `grep`: Search for a specific pattern in files.
        
    11. `chmod`: Change the permissions of a file or directory.
        
    12. `sudo`: Execute a command with administrative privileges.
        
    13. `man`: Display the manual pages for a command.
        
    14. `find`: Search for files and directories based on various criteria.
        
    15. `tar`: Create or extract compressed archive files.
        
    16. `gzip`: Compress files using the gzip algorithm.
        
    17. `gunzip`: Decompress files compressed with gzip.
        
    18. `ssh`: Connect to a remote server using the SSH protocol.
        
    19. `scp`: Copy files between local and remote systems over SSH.
        
    20. `wget`: Download files from the internet.
        
    21. `curl`: Transfer data to or from a server using various protocols.
        
    22. `df`: Display disk usage information.
        
    23. `du`: Estimate file and directory sizes.
        
    24. `top`: Display system resource usage and running processes.
        
    25. `ps`: Display information about active processes.
        
    26. `kill`: Terminate processes by ID or name.
        
    27. `ping`: Send ICMP Echo Request packets to a host.
        
    28. `ifconfig`: Display or configure network interfaces.
        
    29. `netstat`: Display network connection information.
        
    30. `history`: Display previously executed commands.
        
    31. `date`: Display or set the system date and time.
        
    32. `uptime`: Display the system's uptime.
        
    33. `whoami`: Display the current username.
        
    34. `file`: Determine the file type.
        
    35. `chown`: Change the ownership of files or directories.
        
    36. `chgrp`: Change the group ownership of files or directories.
        
    37. `ln`: Create links between files.
        
    38. `alias`: Create a shortcut for a command.
        
    39. `echo`: Print text or variables to the terminal.
        
    40. `sed`: Stream editor for filtering and transforming text.
        
    41. `awk`: Text processing and pattern matching tool.
        
    42. `sort`: Sort lines of text files.
        
    43. `cut`: Extract sections from lines of files.
        
    44. `head`: Output the beginning of files.
        
    45. `tail`: Output the end of files.
        
    46. `diff`: Compare files line by line.
        
    47. `patch`: Apply changes to files using patch files.
        
    48. `ssh-keygen`: Generate SSH key pairs.
        
    49. `ssh-add`: Add private keys to the SSH agent.
        
    50. `scp`: Securely copy files between systems