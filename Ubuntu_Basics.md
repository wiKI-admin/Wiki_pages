# **Ubuntu Basics  
  
Guides and Standards**

|                    |                   |
| ------------------ | ----------------- |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
|                    |                   |
| **Creation date:** | 02.01.2024        |
| **Version 1.0:**   | 02.01.2024        |
| **Author:**        | Chiragkumar Patel |

# **Table of contents**

[1. General 1](#general)

[2. Ubuntu Basics 2](#ubuntu-basics)

[3. Frequently Used Commands 3](#frequently-used-commands)

[4. Creating Bootable USB Stick 7](#creating-bootable-usb-stick)

[5. Crontab 8](#crontab)

## General

**<span class="underline">Purpose:</span>**

*The document aims to provide basic information related to Ubuntu and
its basics. After reading the document, the user will be able to get
familiarize with the Ubuntu OS and have the information related to the
basic commands which are regularly used.*

**<span class="underline">Scope:</span>**

*The document aims to provide step-by-step instructions for beginners
and intermediate users, guiding them about the step-by-step process of
working with an Ubuntu OS. It will cover essential Ubuntu commands.
Additionally, the document will include detailed guidelines for creating
a bootable USB stick in Linux environment to install Ubuntu OS on any
system. The document will also give a basic idea about the crontab in
Ubuntu and how to use it.*

**<span class="underline">Description:</span>**

*This detailed guide provides comprehensive insights into essential
aspects of Ubuntu, a widely used Linux distribution renowned for its
user-friendly interface and stability. The guide is structured into
these key sections:*

1.  *Ubuntu Basics:* *An overview of Ubuntu's foundational elements,
    highlighting its Debian architecture and accommodating environment
    for users of varying expertise levels.*

2.  *Frequently Used Commands:* *A detailed exploration of frequently
    used commands, empowering users with the ability to navigate, manage
    files, execute superuser tasks, and perform essential system
    operations.*

3.  *Creating a Bootable USB:* *Step-by-step instructions on creating a
    bootable USB drive for Ubuntu installation or trial. The guide
    covers downloading the ISO file, formatting the USB drive, and using
    tools like Rufus or dd for the writing process.*

4.  *Crontab Usage: In-depth guidance on utilizing Crontab, the
    time-based job scheduler in Ubuntu. The section covers accessing the
    Crontab file, editing it with timing and commands, and provides an
    illustrative example for effective task scheduling.*

*This comprehensive document aims to serve as a go-to reference for
Ubuntu users, offering both foundational knowledge and practical
instructions to enhance their experience with this powerful Linux
distribution.*

## Ubuntu Basics

Ubuntu is a popular and user-friendly Linux-based operating system (OS)
that is widely used for personal computers, servers, and cloud
computing. It is an open-source operating system, meaning that its
source code is freely available to the public, and users can modify and
distribute it as per the terms of the GNU General Public License (GPL).

Here are some key aspects of Ubuntu:

> **Linux Kernel:** Ubuntu is built on the Linux kernel, which is the
> core part of the operating system that interacts with the hardware.
> The Linux kernel is known for its stability, security, and efficiency.
> 
> **Desktop Environment:** Ubuntu uses a graphical user interface (GUI)
> called the Unity desktop environment (until version 17.04) or GNOME
> (starting from version 17.10). The desktop environment provides users
> with a visually intuitive way to interact with the operating system
> and applications.
> 
> **Package Management:** Ubuntu uses the Debian package management
> system. The Advanced Package Tool (APT) is the command-line tool used
> for managing software packages on Ubuntu. It allows users to easily
> install, update, and remove software applications.
> 
> **Software Center:** Ubuntu Software Center is a user-friendly
> application that allows users to browse, install, and manage software
> packages with a graphical interface. Users can find a wide range of
> free and open-source software available for installation.
> 
> **Community and Support:** Ubuntu has a large and active community of
> users and developers. The Ubuntu community provides support through
> forums, documentation, and other online resources. Canonical Ltd., the
> company behind Ubuntu, also offers commercial support for businesses
> and enterprises.
> 
> **Variants:** Ubuntu comes in different variants, each designed for
> specific purposes. For example:
> 
> <span class="underline">*Ubuntu Desktop*:</span> Designed for personal
> computers and workstations.
> 
> <span class="underline">*Ubuntu Server*:</span> Optimized for server
> environments.
> 
> <span class="underline">*Ubuntu LTS (Long Term Support)*:</span>
> Versions of Ubuntu that receive extended support and updates for five
> years, providing stability for enterprises and organizations.
> 
> *<span class="underline">Ubuntu Kylin:</span>* A version of Ubuntu
> designed for users in China, featuring a customized desktop
> environment and software tailored for Chinese users.
> 
> **Security:** Ubuntu follows a security-first approach. Security
> updates are regularly released to address vulnerabilities and ensure a
> secure computing environment.
> 
> **Compatibility and Hardware Support:** Ubuntu has good hardware
> compatibility and supports a wide range of devices. It includes
> drivers for a variety of hardware components, making it suitable for
> use on various computer systems.
> 
> In summary, Ubuntu is a powerful, user-friendly, and community-driven
> operating system that is well-suited for both personal and
> professional use. It embodies the principles of open-source software,
> providing users with freedom, flexibility, and a robust computing
> experience.

## Frequently Used Commands

> Every command list here has multiple options and several uses. I will
> list the purpose of each command with its basic syntax. The detailed
> description and example of the use of command is given on this link:
> [<span class="underline">https://ubuntu.com/tutorials/command-line-for-beginners\#1-overview</span>](https://ubuntu.com/tutorials/command-line-for-beginners#1-overview) 

1.  > <span class="underline">Ls command: List the contents of a
    > folder</span> 

> This command lets you see what files and folders are in your current
> folder. 

  - > ls 

<!-- end list -->

2.  > <span class="underline">Cd command: Change the directory</span>

> The cd command stands for change directory; with this, you can change
> your location and move to another directory. 

  - > cd 

<!-- end list -->

3.  > <span class="underline">cat command: Read a text file </span>

> If you quickly want to see the contents of a text file in Linux, cat
> is the command you use. It displays the contents on the screen. 

  - > cat filename 

<!-- end list -->

4.  > <span class="underline">less command: Read a large text
    > file</span>

> The cat command is good enough for viewing small text files. But for
> big files when you open a file with less, it opens the file in pages.
> You can scroll up/down, look for text, and more. 

  - less filename 

> Once you are done reading the file, you can exit the less view by
> pressing the Q key. You’ll notice that nothing is displayed on the
> screen. Your screen is clean.

5.  > <span class="underline">mkdir command: Make new folders </span>

> While there is no specific command for creating new files, there is a
> dedicated command for making new folders (or directories, as we call
> them in Linux). 

  - > mkdir new\_dir 

<!-- end list -->

6.  > <span class="underline">cp command: Copy files and folders </span>

> Copying files and folders in the command line is also one of the
> common tasks you will encounter. The cp command, short for copy, is
> used for this purpose. 

  - > cp existing\_file.txt existing\_file.back 

> You can use the same cp command for copying directories as well. For
> that, you must specify the recursive option -r: 

  - > cp -r dir another\_location 

<!-- end list -->

7.  > <span class="underline">mv command: Cut paste or rename files and
    > folders</span>

> The mv command stands for ‘move’. When you copy a file to another
> location, it remains in its original place. The mv command moves the
> files and folders to the other location. You can think of it as a
> cut-paste operation. 

  - > mv file.txt /another/location 

> You can use the mv command to rename the file as well. 

  - > mv file.txt new\_file.txt 

<!-- end list -->

8.  > <span class="underline">rm command: Remove files and
    > folders</span>

> You use the rm (short for remove) command to delete files in the Linux
> terminal. 

  - > rm filename 

> There is no undo option after you delete files in the command line.
> This is why you should be extremely careful while deleting files. If
> you are afraid of deleting the wrong file, use the interactive mode
> with option -i, which gives you an additional prompt to confirm the
> action. 

  - > rm -i filename 

<!-- end list -->

9.  > <span class="underline">Nano: Edit files </span>

> To edit an existing file in Nano, use: 

  - > nano filename 

> To save (or discard changes) and exit the editor interface, use the
> Ctrl+x keys. 

10. > <span class="underline">clear: Clear terminal screen </span>

> The clear command clears the terminal. That’s it. 

  - > clear 

> And why do you need to do that? Well, if your terminal screen is
> flooded with random stuff and you want to do something new. Cleaning
> the terminal is like cleaning the board or opening a new page in your
> notebook. 

11. > <span class="underline">ps: Check and handle processes </span>

> The ps command is for handling the processes running on your system.
> Each process has an associated ID called PID, which can be used for
> various purposes, such as terminating a process. To see all the
> processes running by all users, use: 

  - > ps aux 

> This will give a massive list of processes and more details about
> them 

12. > <span class="underline">Top: System Monitor </span>

> While the ps command gives you all the running processes, the top
> command gives you a real-time view of the processes and the system
> resource consumption. 

  - > top 

<!-- end list -->

13. > <span class="underline">lsblk: List disks and partitions </span>

> The lsblk command lists all the block devices on your system. In
> really simple (and not entirely technically accurate) terms, it
> displays the disks and partitions. 

  - > lsblk 

<!-- end list -->

14. > <span class="underline">fdisk: List and manage disks and
    > partitions </span>

> Another similar but better command is the fdisk command. It lets you
> manipulate the disk partitions. This means you can create new
> partitions and delete and resize existing ones with this command. 

  - > sudo fdisk -l 

<!-- end list -->

15. > <span class="underline">find: Search for files </span>

> The find command is an extensive and versatile command for this
> purpose. It has more than fifty options, and you will probably never
> need all of them. Here’s an example of the find command that will give
> you all the files that end with .txt extension in the current
> directory. 

  - > find . -type f -name "\*.txt" 

<!-- end list -->

16. > <span class="underline">grep: Search in file content </span>

> The find command searches for files based on their name and type. If
> you want to search based on the content of the files, you use the grep
> command. 

  - > grep -ri search\_term 

<!-- end list -->

17. > <span class="underline">kill: Terminate processes </span>

> If you have a misbehaving process that takes too many system
> resources, you can find it and then terminate it using the kill
> command. 

  - > sudo kill -9 process\_ID\_or\_Name 

<!-- end list -->

18. > <span class="underline">history: Look back into what commands you
    > ran in the past </span>

> In Ubuntu, your shell keeps a history of the commands you run. Enter
> history in the terminal, and you should see a history of commands you
> ran in the past. 

  - > History 

<!-- end list -->

19. > <span class="underline">chmod: Change file permissions </span>

> The chmod (change mode) command is used to change a file's
> permissions. 
> 
> The most common use of this command is when you want to make a file
> executable. Got a shell script? Make it executable like this: 

  - > chmod u+x file executable 

<!-- end list -->

20. > <span class="underline">lshw: Get the hardware details </span>

> It displays a vast output with details about all the hardware
> components and trust me, that’s not very easy to understand. The
> output of lshw is divided into classes and you can use that to show
> the details for a class of hardware. 

  - > Lshw 

<!-- end list -->

21. > <span class="underline">sudo: Run commands with root
    > privileges </span>

> You must have noticed that I used sudo as a prefix for some commands I
> discussed previously. 
> 
> By default, in Ubuntu, sudo is configured in a way that it allows you
> (to the default admin user) to run any command with root privileges. 

  - > Sudo your\_command 

<!-- end list -->

22. > <span class="underline">apt: Install, remove, and manage .deb
    > packages </span>

> The apt command is used for managing packages in Ubuntu. You’ll have
> to use it with sudo as these are administrative tasks. 
> 
> To install a package, use: 

  - > sudo apt install package\_name 

> To delete an installed software, use: 

  - > sudo apt remove package\_name 

<!-- end list -->

23. > <span class="underline">snap: Install, remove and manage snap
    > packages </span>

> To find a package, use: 

  - > snap find search\_term 

> To install a package, use: 

  - > sudo snap install package\_name 

> To list installed snap applications: 

  - > snap list 

> To remove an installed Snap application, use: 

  - > sudo snap remove package\_name 

<!-- end list -->

24. > <span class="underline">ip: Check IP address and other
    > info </span>

> The ip command lets you check your IP address. You can also see and
> manipulate the routes, network devices, and more. 

  - > ip a 

<!-- end list -->

25. > <span class="underline">ping: Check if the remote system is
    > reachable </span>

> Ping is another Linux networking command you should be aware of. To
> check whether a remote system is available or not, give its IP address
> to the ping command: 

  - > ping ip\_address 

<!-- end list -->

26. > <span class="underline">ssh: Connecting to remote systems </span>

> SSH is used for connecting to other Linux systems from your terminal. 

  - > ssh user@ip\_address\_of\_remote\_system 

> You need to know the user and password of the remote system, of
> course. 

27. > <span class="underline">scp: Copy files between remote
    > systems </span>

> The scp command works almost like the cp command you saw earlier.
> Here’s an example that copies the file from the home directory of
> the user on the remote system to the current directory of your locally
> logged in system. 

  - > scp username@ip\_address:/home/username/filename 

<!-- end list -->

28. > <span class="underline">man: Learn about commands in
    > detail </span>

> All Linux systems come with a manual for the commands. It’s called
> manpage, and you can access the manual page of an installed command
> with the following: 

  - man command\_name

## Creating Bootable USB Stick

> With a bootable Ubuntu USB stick, you can 1.) Install or upgrade the
> ubuntu 2.) Test out the Ubuntu desktop experience without touching the
> predefined PC configuration 3.) Boot into Ubuntu on a temporary
> machine 4.) Repair or fix a broken configuration. 
> 
> The user needs to have a USB stick with minimum 4GB storage capacity,
> Ubuntu desktop 14.04 or later pre-installed, and an Ubuntu ISO file
> which can be downloaded from Ubuntu’s website. 

<span class="underline">Steps for creating a bootable USB stick with
Ubuntu itself</span> 

  - Insert USB stick and select ‘Do Nothing’ if a prompt opens up 

  - On Ubuntu 18.04 and later, use the bottom left icon to open ‘Show
    Applications’. In older versions of Ubuntu, use the top left icon to
    open the dash 

  - Use the search field to look for Startup Disk Creator 

  - Select Startup Disk Creator from the results to launch the
    application 

  - When launched, Startup Disk Creator will look for the ISO files in
    your Downloads folder, as well as any attached USB storage to which
    it can write. 

  - It’s likely that both your Ubuntu ISO and the correct USB device
    will have been detected and set as ‘Source disc image’ and ‘Disk to
    use’ in the application window. If not, use the ‘Other’ button to
    locate your ISO file and select the exact USB device you want to use
    from the list of devices 

  - Click Make Startup Disk to start the process. 

  - Click Make Startup Disk to start the process. 

  - Confirm USB device 

  - You now have Ubuntu on a USB stick, bootable and ready to go.

## Crontab

> Crontab is a time-based job scheduler in Unix-like operating systems.
> It allows users to schedule jobs (commands or scripts) to run
> periodically at fixed times, dates, or intervals. Crontab is a
> contraction of "cron table," where cron stands for the time-based job
> scheduler in Unix-like operating systems. Crontab is a powerful tool
> that automates repetitive tasks, making it an essential component for
> system administrators and users alike. 

Here are some key aspects of crontab, 

1.  **Basic Concepts:**

> Cron Jobs: These are the scheduled tasks that you want to run at
> specified intervals. 
> 
> Crontab: The crontab command is used to manage and maintain the cron
> jobs for each user. 

2.  **Crontab Syntax:** 

A crontab file consists of lines, each representing a cron job. 

Each line follows a specific syntax: 

  - > \* \* \* \* \* command\_to\_be\_executed 

> The five asterisks represent minute, hour, day of the month, month,
> and day of the week, respectively. Asterisk (\*) means "any" or
> "every." You can replace it with specific values or ranges. 

3.  **Examples:** 

To run a job every day at 2 AM: 

  - > 0 2 \* \* \* command\_to\_run 

To run a job every Monday at 8 PM: 

  - > 0 20 \* \* 1 command\_to\_run 

<!-- end list -->

4.  **Special Strings:** 

<span class="underline">@reboot</span>: Run the command once at
startup. 

> <span class="underline">@yearly</span>,
> <span class="underline">@annually</span>,
> <span class="underline">@monthly</span>,
> <span class="underline">@weekly</span>,
> <span class="underline">@daily</span>,
> <span class="underline">@hourly</span>: Predefined schedules for
> common intervals. 

5.  **Editing the Crontab:** 

Use the ‘<span class="underline">crontab -e’</span> command to edit the
crontab file. 

> The file is opened in the default text editor specified by the
> ‘<span class="underline">VISUAL’</span> or
> ‘<span class="underline">EDITOR’</span> environment variables. 

6.  **Listing and Removing Jobs:** 

<span class="underline">‘crontab -l’</span>: Lists the user's current
cron jobs. 

<span class="underline">‘crontab -r’</span>: Removes all user's cron
jobs. 

7.  **Logging:** 

> Cron jobs typically send output (stdout and stderr) to the user's
> email. You can redirect it to a file by appending
> ‘<span class="underline">\>\> /path/to/logfile 2\>&1’</span> to the
> command. 

8.  **Security Considerations:** 

> Ensure that the scripts or commands executed by cron jobs have
> appropriate permissions. Be cautious when using sensitive information
> like passwords in scripts. 

9.  **Common Issues:** 

> Cron jobs might not have the same environment variables as your user
> session. Specify full paths to commands and files to avoid issues. 

10. **Examples of Use Cases:** 

<span class="underline">Automated Backups:</span> Schedule backups of
important files or databases. 

<span class="underline">Periodic Maintenance:</span> Run scripts for
system cleanup or updates. 

<span class="underline">Data Synchronization:</span> Schedule tasks to
keep data in sync. 

So, in conclusion, Crontab is a powerful tool for automating repetitive
tasks on Unix-like systems. By understanding its syntax and features,
users can schedule jobs to run automatically, saving time and ensuring
that critical tasks are performed consistently. However, it's crucial to
use crontab with caution, especially when dealing with important system
tasks, and to regularly review and update scheduled jobs as needed. 

More detailed explanation with the examples can be found on ubuntu
community on following link:
[<span class="underline">https://help.ubuntu.com/community/CronHowto</span>](https://help.ubuntu.com/community/CronHowto)
