# **Linux**

## **Parts of Linux**
- Bootloader - software that manages the boot process of computer (splash screen that pops up and goes away to boot into OS)
- Kernel - core of the system, manages the CPU, memory, and peripheral devices; lowest level of the OS but this piece is called “Linux”
- Daemons - background services (printing, sound, scheduling, etc) that either start-up during boot or after user logs in
- Shell - command process that allows you to control the computer via commands typed into a text interface; program that exposes the computer’s OS to a user or program; the shell presented in a terminal is a command line interpreter
- Command Line Interface - user interface managed by a command line interpreter program which processes commands to a computer program and outputs the results
- Graphical Server - sub-system that displays the graphics on your monitor; AKA “X server” or “X”
- Desktop Environment - user interface (ex. Unity, GNOME, CInnamon); each desktop environment includes built-in applications like file managers, configuration tools, web browsers, games, etc
- Applications - thousands of high-quality software titles that can be installed
- Distributions - operating systems based on Linux are known as Linux distributions or distros (ex. Debian, Ubuntu, Fedora, CentOS, Gentoo, Arch Linux)
- Terminal - input/output environment that presents a text-only window running a shell (the black box where you can run commands and see the results printed out to the terminal) (CTRL/ALT/T opens new terminal)

## **Filesystem Hierarchy Standard**
- Nearly all Linux distributions are compliant with a universal standard for filesystem directory structure (Filesystem Hierarchy Standard)
- FHS defines a set of directories, each of which serve their own special function
- Forward slash (/) is used to indicate the root directory in the filesystem hierarchy defined by the FHS
- When a user logs in to the shell, they are brought to their own user directory, stored within /home/ (user’s home directory)
- Root user has its own home directory specified by the FHS /root/ (/is referred to as the root directory, and it is different from root/, which is stored within /***

## **Navigation**
- Linux file systems are based on a directory tree
- $ indicates you are working as a user or root
- / indicates you are working as a superuser
- You can create directories (functionally identical to folders found in other OS) inside other directories, and files can exist in any directory
- To see what directory you are currently active in, you can run the pwd command (print working directory)
- Pwd command prints the path to your current directory
     - sammy@linux-machine:~$ pwd (sammy is the user logged in, linux-machine is the machine in use)
    - Output /home/sammy
    - This output indicates that the current active directory is sammy, which is inside the home/ directory, which lives in the root directory /
- Ls command will return a list of names of any files or directories held in your current working directory
    - Subdirectories are shown in blue
    - Files are shown in white
    - Colors can change, depending in the Linux version you are using
    - The first character specifies if the current item is a directory (showing a “d”) or a file (showing a “-”)
    - The following letters are read taking groups of 3 characters; the 1st one sets the author permissions, the 2nd one the group permissions, and the 3rd one any external user outside the specified group
    - Granted permissions
        - R - reading
        - W - editing
        - X - execution
- Chmod command allows changes to permissions
    - Type chmod command followed by options and file name interested
    - Ex. u-x option removes the execute x permission from the author user u
    - Ex. u+wx adds editing and execute permissions to the author u 
    - You can also use g and o for u to manage groups or others 
    - Chmod command only works if you are the original author or the administrator
- Ls-l command will give you more information, including file permissions, the author name and group, the size in bytes and the last modification date
- Mkdir command (make directory) will create one or more new directories within your current working directory
    - Ex. to create two new directories named testdir1 and testdir2, you might run the following command:
    - sammy@linux-machine:~$ mkdir testdir1 testdir2
    - When you run the ls command, these directories will appear in the output:
    - sammy@linux-machine:~$ 1s
    - Output testdir1 testdir2
- Cd command (change directory) is used to navigate into a different directory
    - sammy@linux-machine:~$ cd testdir1
    - Use TAB key to autocomplete the name
    - This will change your new current working directory to the directory you specified; you can see this with pwd
    - sammy@linux-machine:~/testdir1$ pwd
    - Output /home/sammy/testdir1
    - Because testdir1 and testdir 2 are both held in the sammy user’s home directory, they reside in different branches of the directory tree
    - The cd command looks for directories within your current working directory, so you cannot cd directly into the testdir2 directory while testdir1 is your working directory
    - You can navigate to any directory if you specify the full path of the directory you want to navigate to
        - Ex. cd sammy@linux-machine:~/testdir1$  cd  /home/sammy/testdir2
    - In Linux, a tilde (~) is shorthand for the home directory of the user you’re logged in as
        - Could write previous command as sammy@linux-machine:~/testdir1$  cd  ~/testdir2 and rec’d same result
    - Can specify .. to change to the directory one level up in your path
        - sammy@linux-machine:~/testdir1$  cd  ..
    - If you’re ever confused about where you are in the command tree, you can always run the pwd command to find your current directory

## **File Manipulation**
- You cannot use cd command to interact with files as it only allows you to navigate directories
- Touch command allows you to create new files
    - Ex. To create a new file called file.txt, you would enter:  $  touch  file.txt
    - This creates an empty file with the name file.txt in your current working directory
- Mv command (move) allows you to move a file or directory from one place to another
    - By specifying the original file (file.txt) you can move it to a new location in the current working directory, thereby renaming it
    - ./
    - Can specify a new name after the destination path to rename the file as you move it
- Cp command (copy) allows you to copy a file to a new location
    - Ex. if you want to bring back file.txt but keep newfile.txt, you can make a copy of newfile.txt named file.txt
    - $  cp  newfile.txt  file.txt
    - Type the file name and its destination path
- Cp -r command allows you to copy an entire folder with all its content inside
    - $  cp  -r  ./Green  ./White would copy the green folder and its content into the white folder, keeping the original green folder where it is
- To add text to files, can use nano command
    - $  nano  file.txt
    - This will open up a space where you can immediately start typing to edit file.txt
    - To save your text, presse CTRL + X, Y, and the ENTER
    - This returns you to the shell with a newly saved file.txt file
    - Now that file.txt has some text in it, you can view it using cat or less
- Cat command prints the contents of a specified file to your system’s output
    - $  cat  file.txt
    - This will print out the entire contents of file.txt to the terminal
- Less command allows you to paginate the output
    - $  less  file.txt
    - Allows you to view the content
    - Allows you to print one terminal page at a time beginning at the start of the file
    - Use spacebar to advance a page, or the arrow keys to go up and down one line at a time
    - Press q to quit out of less
- Rm command (remove) allows you to delete a file
    - $  rm  file.txt
    - Without other options, the rm command cannot be used to delete directories
    - However, it does include the -d flag which allows you to delete empty directories
    - $  rm  -d  directory 
    - Can also remove empty directories with the rmdir command
    - $  rmdir  directory
    - If you want to delete a directory that isn’t empty, you can run rm with the -r flag; this will delete the specified directory along with its contents, including any files and subdirectories (*careful with this!)
    - $  rm  -r  directory
- History command will give you a full list of all the commands executed in order
- Use clear command to clear (delete) the contents of the whole terminal
- Execute command allows you to execute any file
    - ./exec.

## **How to Search for Answers to Linux Questions**
- Google
- DuckDuckGo
- Stack Exchange
- DigitalOcean’s Community Q&A
- Linux manual pages offer detailed documentation of nearly every command
    - To see the manual page for any command, pass the command’s name as an argument to the man command
    - $  man  command
    - Ex. $  man  rm displays the purpose of rm, how to use it, what options are available, and examples of use


