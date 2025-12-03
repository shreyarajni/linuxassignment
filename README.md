Linux Programming: Assignment-1
NAME- Shreya Rajni 
SECTION-3A 
ROLL NO.-59 
USN- ENG24CY0161 



1.What is Linux Operating System (OS)? List three pros and cons of it. (CO1) 
Linux is an open-source operating system based on UNIX. It is responsible for managing the hardware of a computer, running the users' applications, and supporting multi-user and multitasking environments. 
Pros: It is a free product and its source code is available to only view, very secure and is extremely stable which is the reason why servers are running on it. 
Cons: There isn't a full range of commercial apps that support Linux, command-based work is hard for beginners, and additionally, in some cases, there may be no hardware drivers available. 

2.Differentiate between Linux, Mac, Android, and Windows OS with at least six unique features.
Linux is an open source operating system mainly used in servers. It is also possible to use it on desktops, but its use is mostly limited to environments jnvolving technology. Linux is completely customizable, offers high security, and software installation is carried out via package managers such as apt or yum. 
MacOS is a proprietary operating system built only for Apple devices. Its primary features are good UI, tight security, and excellent integration with the rest of the Apple ecosystem. The advantage of customization is limited because Apple is controlling both hardware and software. 
Same goes for Android. Despite this, it is mainly utilized in smartphones and other touchscreen gadgets. The operating system is open but Google is the maintainer. To install apps, one has to use Play Store or APK files. 
On the other hand, Windows is a proprietary operating system tailored for typical desktop usage. It is compatible with a plethora of software, games, and drivers. Also, for installation purposes, it uses EXE/MSI files. Additionally, this platform is the most commonly found in offices and homes. 
In simple words: Linux = most customizable, Mac = polished but restricted, Android = mobile Linux, Windows = user-friendly and widely supported. 
3.Why is Linux preferred for Mainframe Servers for legacy application? Give three out-of-the-box technical reasons.
One of the reasons that explains why Linux is preferred is that it allows changes at the kernel level to be done which is how the system can be adjusted for heavy mainframe workloads. Another good point is very robust process isolation which is due to use of tools like cgroups, namespaces, and SELinux. Also, the reason for the longest uptime is another one - Linux is able to operate non-stop for several years without rebooting, which is a must for old enterprise applications. 
4.Explain the structure of the Linux File System with proper diagram. Note: you can use the tree command to find it out.
Linux has a tree-like file system that goes all the way back to the root /. 
/bin is the folder that has the basic commands, /sbin is the folder with system commands, /etc is the folder that has the configuration files, /home is the folder for user files, /var is the folder that holds log files, /boot is the folder for kernel and bootloader files, /lib is the folder for libraries, and /tmp is the folder for temporary data. 
Small diagram: 
/
├── bin
├── boot
├── dev
├── etc
├── home
├── lib
├── sbin
├── tmp
└── var
5. How Red Hat earns money if Linux is open-source 
Red Hat's main source of revenue is enterprise subscriptions where the companies pay for the official updates, security patches, long-term support, and certifications. They also offer paid training (like RHCE), cloud platforms such as OpenShift, and automation tools such as Ansible. In a nutshell, what they do is not selling Linux but selling the support, the reliability, and the enterprise services. 
6. Command for today's date/time 
date 
7. Command to check system uptime 
uptime 
8. Difference between shutdown -h now and halt 
The command shutdown -h now shuts the system down in a safe manner by stopping the various running services and unmounting the disks. 
Halt on the other hand is the command that stops the system right away and thus may not unmount discs properly. Therefore, shutdown -h now is the safer option. 
9. init 0 vs shutdown -h (which is safer) 
The command init 0 changes the system to runlevel 0 and shuts down the system very quickly. The command shutdown -h does a clean and a graceful shut down by warning the users and closing the services. Therefore, shutdown -h is safer. 
10. Problems if a server is powered off without proper shutdown 
Corruption of file systems is one of the consequences that might occur after such an event, open transactions in databases could be lost, logs may be in an inconsistent state, and some hardware components such as hard drives can get damaged due to the abrupt removal of power. 
Brainstorming 
a) Can we build our own OS using Linux kernel? 
Yes, the Linux kernel is an open-source project and hence anyone is free to compile it and create their own operating system. 
b) Challenges in building your own OS 
Deep knowledge of kernel internals is required, hardware drivers are not that easy to figure out because they are often not documented, keeping the security updates coming is not an easy task, and creating a complete package ecosystem takes a lot of time. 
c) Engineers in India working in this field 
Among the Indian contributors are Balasubramaniam Mani (IBM Linux performance), Siddhesh Poyarekar (Red Hat, glibc), Srivatsa S. Bhat (Linux memory management), and Anil Venkatesh (kernel debugging & file ‍‌‍‍‌‍‌‍‍‌systems)



Linux Programming: Assignment-2
NAME- Shreya Rajni 
SECTION-3A 
ROLL NO.-59 
USN- ENG24CY0161 


1.What does the command pwd, whoami and hostname display? (CO1)
pwd gives the directory path of the current folder you are in. 
whoami prints the name of the user that is logged in. 
hostname gives the name of your computer/machine in the ‍‌‍‍‌‍‌‍‍‌network. 

2. Write the command to create a directory named “project” inside the /home/student folder and keep three .txt file into it. Give output snapshot. (CO1)
mkdir /home/student/project
touch /home/student/project/file1.txt /home/student/project/file2.txt /home/student/project/file3.txt
OUTPUT:
ls /home/student/project
file1.txt  file2.txt  file3.txt

3. Explain the difference between absolute path and relative path with proper examples. (CO2) 
An‍‌‍‍‌‍‌‍‍‌ absolute path always begins at the root / and indicates the entire path to a file or folder.
Example:<br>/home/student/project/file1.txt
A relative path is starting from the directory you are and it doesn't refer to the root /.
Example:<br>If you are in /home/student directory, then<br>cd project<br>is a relative ‍‌‍‍‌‍‌‍‍‌path.

4. What command will give you the already executed command traces in the terminal. Give output snapshot. (CO1) 
The command is:
History
Sample Output:
1  ls
2  cd /home
3  mkdir project
4  history

5. Compare the working functionality of find and locate command. Which one is faster and why? (CO1)
find‍‌‍‍‌‍‌‍‍‌ is a real-time tool that goes through the filesystem step by step. It is slower but always accurate as it takes the actual disk into consideration. 
on the other hand, locate depends on a pre-built database (mlocate.db). It is very fast as it doesn't go to the disk to search but rather to the database. 
Therefore locate is quicker as it refers to a stored index rather than performing a ‍‌‍‍‌‍‌‍‍‌scan. 


 6. Which command is used to modify file permissions in Linux? Give an example. (CO1)

Bash
chmod 755 file.txt


7. A file has permissions -rw -r- -r- -. What does this mean? (CO1) 
-rw-r--r-- stands for: 
Owner: reading + writing 
Group: reading only 
Others: reading only 
Only the owner is allowed to change the ‍‌‍‍‌‍‌‍‍‌file



8. Explain the difference between chown and chgrp with an example. (CO1) 
chown changes the owner of a file. 
Example: 
chown student file.txt 

chgrp changes only the group of the file. 
Example: 
chgrp staff ‍‌‍‍‌‍‌‍‍‌file.txt</p 


9. A file needs to be accessible by multiple users but only writable by the owner. How will 
Use: 
chmod 644 filename 
Owner: read + write 
Group: read 
Others: ‍‌‍‍‌‍‌‍‍‌read 

10.How do you check the manual page for any Linux commands? (CO1)
Use the man command:
man ls
This opens the manual page for the command.





Linux Programming: Assignment-3 
NAME- Shreya Rajni 
SECTION-3A 
ROLL NO.-59 
USN- ENG24CY0161 

1.Distinguish between man and whatis commands? Justify with proper example. (CO1) 
Man‍‌‍‍‌‍‌‍‍‌ provides a complete manual page for a command. It includes detailed explanation, options, and examples. Whatis, on the other hand, provides only a one-line summary of the command.

Example:<br> 

man ls → will open a full manual which will explain in detail what ls is.<br> 

whatis ls → will print something like: ls (1) - list directory ‍‌‍‍‌‍‌‍‍‌contents.

‍‌‍‍‌‍‌‍2.Use the tee command to save the output of ls -l into a file while also displaying it. (CO4) 
ls -l | tee output.txt

3.Explain with an example how the tee command can be used in logging. (CO4) 
The tee command is helpful when you want to see the output on the screen and save it to a log file at the same time.
Example:
ping google.com | tee pinglog.txt
This displays the ping output on the terminal and also stores it in pinglog.txt for later review. This is commonly used for debugging or collecting logs.


4.List the steps involved in installing Ubuntu 25.04 LTS on Oracle VirtualBox. (CO2)
Get‍‌‍‍‌‍‌‍‍‌ the Ubuntu 25.04 ISO from the official Ubuntu site.
Get‍‌‍‍‌‍‌‍‍‌ the Ubuntu 25.04 ISO from the official Ubuntu site.
Launch VirtualBox and hit the New button to set up a new virtual machine.
Put in a name and select Linux → Ubuntu (64-bit).
Set aside memory (4GB at least is recommended).
Make a virtual hard disk (20GB or more).
Go to the VM settings → Storage → and insert the Ubuntu ISO into the Optical Drive.
Power the VM on; Ubuntu setup will be there.
Choose Install Ubuntu, select keyboard layout, and choose installation type.
Set up a username and password.
Finish the installation and power off the ‍‌‍‍‌‍‌‍‍‌VM.

5. During Ubuntu OS installation, you face a Kernel Panic Error. How would you troubleshoot it? (CO3) 
If‍‌‍‍‌‍‌‍‍‌ a kernel panic pops up while you are installing, testing these options can help:
First of all, make sure that the ISO file is not corrupted, and if it is, download it again.
Give more RAM to your virtual machine, or add more cores to the CPU.
In the VM configuration, turn on PAE/NX, VT-x/AMD-V or hardware virtualization.
Switch the VirtualBox graphics controller to VMSVGA.
In the VM settings, turn off any USB or network devices that you are not using.
Would the installation start if you try Safe Graphics ‍‌‍‍‌‍‌‍‍‌Mode?
6. Write the command to display the system’s hostname? How to change hostname using sysctl command? (CO1) 
Display hostname:
hostname

Change hostname using sysctl:
sudo sysctl kernel.hostname=newname


7. Which command is used to show the calendar of the year 1984 with August month? (CO1) 
Command to show calendar of year 1984 with August month (CO1)
cal 8 1984

8. Write a command to display system uptime and logged-in users together. (CO3) 
Command to display system uptime and logged-in users together (CO3)
w
(or)
uptime && who

9. Use the find command to list all “.c” files in /home/user. (CO1) 
all .c files in /home/user (CO1)
find /home/user -name "*.c"

10. How do you change file permissions to allow only the owner to read and write? (CO1)
Change file permissions to allow only the owner to read and write (CO1)
chmod 600 filename




Assignment 4
NAME- Shreya Rajni 
SECTION-3A 
ROLL NO.-59 
USN- ENG24CY0161 
1. Using grep + tee to extract usernames from /etc/passwd (CO4)
Usernames‍‌‍‍‌‍‌‍‍‌ can be found in each line before the first colon.
Command:
grep -o '^[^:]+' /etc/passwd | tee usernames.txt
With this, the usernames are extracted and saved in the file usernames.txt, and at the same time, the screen displays the ‍‌‍‍‌‍‌‍‍‌usernames.________________________________________
2. Troubleshooting a binary not found in $PATH using which, find, locate (CO3)
Initially,‍‌‍‍‌‍‌‍‍‌ try to check if the command exists in any directories that are listed in $PATH by using: 
which commandname 
If it is not found, then do the manual searching of the filesystem: 
find / -name commandname 2>/dev/null 
Alternatively, you can use the faster locate database: 
locate commandname 
Once you have found the actual binary location, you can add it to PATH by changing the: 
export ‍‌‍‍‌‍‌‍‍‌PATH=$PATH:/path/to/binary 
________________________________________
3. Pipeline to find .log files modified in last 24 hours in /var/log and save to log_report.txt (CO4)
find /var/log -name "*.log" -mtime -1 | tee log_report.txt
________________________________________
4. Difference between shutdown -r now and reboot (CO1)
shutdown -r now performs a clean shutdown and then restarts the system after stopping services safely.
reboot immediately restarts the system and may skip some shutdown routines on certain systems.
Therefore, shutdown -r now is the safer method.
________________________________________
5. Using tee to debug a script that outputs both stdout and stderr (CO4)
You can capture both normal output and error messages by redirecting stderr to stdout and then using tee.
Example:
./myscript.sh 2>&1 | tee debuglog.txt
This shows everything on screen and saves it into debuglog.txt.
________________________________________
6. Three real-world applications of Linux in industries (CO2)
1.	Servers and Cloud Platforms – Most web servers, data centers, and cloud systems (AWS, Azure, Google Cloud) run Linux.
2.	Embedded Systems – Smart TVs, routers, car infotainment systems, industrial machines use Linux-based firmware.
3.	Cybersecurity and Networking – Tools like Kali Linux, firewalls, intrusion detection systems, and network appliances are Linux-based.
________________________________________
7. Difference between application, system, and utility software in Linux (CO2)
Application software refers to programs used by end-users, such as browsers, editors, media players, or office applications.
System software includes the kernel and core components that manage hardware and provide system services.
Utility software consists of helper tools like file managers, backup tools, compression commands, and disk check utilities that support the system but are not full applications.
________________________________________
8. Key differences between open-source and proprietary operating systems (CO2)
Open-source OS provides full access to source code, can be modified freely, and is distributed without licensing restrictions.
Proprietary OS hides its source code, restricts modification, and requires paid licenses.
Open-source systems rely on community contributions, while proprietary systems depend on a single company for updates and support.
________________________________________
9. Command to display system kernel version (CO3)
uname -r
________________________________________
10. Difference between head and tail commands (text processing)
head shows the first few lines of a file (default 10).
tail shows the last few lines of a file.
They help preview the beginning or end of large text files.


Assignment 5 

NAME- Shreya Rajni 

SECTION-3A 

ROLL NO.-59 

USN- ENG24CY0161 

1. What is a Bash shell script? Give one example. 

Think of a Bash shell script as your personal to-do list for the computer . It’s just a simple text file packed with Linux commands that the Bash interpreter runs one after the other. It's how you automate those boring, repetitive tasks! 

A script always starts with the shebang line, #!/bin/bash, which tells the system, "Hey, use the Bash program to run this file!" 

Example: A simple script to back up a user's Documents folder. 

#!/bin/bash 
# Backup the Documents folder to a timestamped tar archive 
DATE=$(date +%Y%m%d) 
tar -czf ~/backup-$DATE.tar.gz ~/Documents/ 
echo "Backup successful: backup-$DATE.tar.gz created." 
  Assignment 6 

NAME- Shreya Rajni 

SECTION-3A 

ROLL NO.-59 

USN- ENG24CY0161 

 

Q1. Which command is used to list the contents of a directory? 

Answer: 

ls 

 Lists all files and folders in the current directory. 
Example: 

ls /home 

Shape 

Q2. Write the command to create a new directory named 123test_dir. 

Answer: 

mkdir 123test_dir 

 Creates a folder with the name 123test_dir. 

Shape 

Q3. What is the purpose of the sed command? 

Answer: 
sed stands for Stream Editor, used to search, find, replace, insert, or delete text in files. 

Example: 

sed 's/linux/unix/' file.txt 

 Replaces the word linux with unix in each line. 

Shape 

Q4. Which distinct command is used to display one-line descriptions of any commands? 

Answer: 

whatis command_name 

 Example: 

whatis ls 

Displays a short description of the ls command. 

Shape 

Q5. Write the command to create an empty file named notes.txt. 

Answer: 

touch notes.txt 

 Creates an empty file or updates timestamp if it already exists. 

Shape 

Q6. Differentiate between grep and awk commands. 

Answer: 

Feature 

grep 

awk 

Purpose 

Search for patterns 

Process and analyze text (fields/columns) 

Output 

Prints matching lines 

Can print specific columns or compute 

Example 

grep "error" log.txt 

awk '{print $1, $3}' log.txt 

Shape 

Q7. Write the command to give read, write, and execute permission to the owner of a file script.sh. 

Answer: 

chmod u+rwx script.sh 

 Gives all permissions to the user (owner). 

Shape 

Q8. How is chown different from chgrp? Give one example for each. 

Answer: 

Command 

Function 

Example 

chown 

Changes file owner 

sudo chown user file.txt 

chgrp 

Changes file group 

sudo chgrp staff file.txt 

Shape 

Q9. A user cannot execute a file even though it exists. How to troubleshoot using ls -l, chmod, and whoami? 

Answer: 

Check permissions: 

ls -l file.sh 

Check current user: 

whoami 

If execute permission missing, add it: 

chmod +x file.sh 

Shape 

Q10. Command pipeline to find all .log files modified in last 2 days in /var/log, display them and save results to recent_logs.txt. 

Answer: 

find /var/log -name "*.log" -mtime -2 | tee recent_logs.txt 

 Displays the list on screen and saves it in recent_logs.txt. 
 
 

2. Write a simple shell script to print “Hello World”. 

This is the classic, simplest script! All you need is the shebang and the trusty echo command: 

#!/bin/bash:Hello World Script:hello_world.sh 
echo "Hello World" 
 
 

3. What is the purpose of comments (#) in a shell script? 

Comments (#) are your way of leaving notes for yourself (and others!) inside the script. They’re super important for two main reasons: 

Explanation: They help explain what your complicated code blocks or functions are doing, making the script readable and maintainable. 

Exclusion: During testing or debugging, you can use them to temporarily "hide" lines of code without deleting them. 

The great thing is, the shell interpreter ignores anything that starts with a # (unless it's inside quotes). 

4. How do you declare variables (int, float, double, string, Boolean, and char) in a shell script? 

This is where Bash is pretty chill! It's dynamically and weakly typed, meaning you don't have to stress about declaring specific types like int or float. Variables are like temporary sticky notes—you just name them and assign a value, and Bash treats it all as text (strings) by default. 

Declaration/Assignment Syntax: 

# General Syntax for any type (stored as a string) 
VARIABLE_NAME="Value" 
 
# Example String 
GREETING="Hello" 
 
# Example Integer (used in arithmetic context) 
# The 'declare -i' helps Bash treat it strictly as an integer for math. 
declare -i AGE=30 
 
# Note: For decimal math, you have to use external tools like 'bc'. 
RESULT=$(echo "5.5 * 2.1" | bc) 
 
 

Friendly Reminder: Explicit types like float, double, Boolean, and char don't really exist in standard Bash; you manage complex values using string manipulation or external utilities. 

5. Write a shell script to display the current date and time of the system. 

The date command is your friend here! You can use it alone for the full timestamp, or use formatting options to get specific views: 

#!/bin/bash:Display Date and Time:system_time.sh 
echo "Current System Date and Time:" 
date 
echo "Formatted time (Year-Month-Day Hour:Min:Sec):" 
date +"%Y-%m-%d %H:%M:%S" 
 
 

6. Explain the difference between a constant and a variable in bash script. 

This is a key security and stability concept: 

Feature 

Variable 

Constant 

Flexibility 

Its value can be changed throughout the script's execution. 

Its value, once set, cannot be changed or unset. 

Syntax 

MY_VAR="initial_value" 

readonly MY_CONSTANT="fixed_value" 

Use Case 

Storing temporary results, counters, or user input. 

Storing fixed values like application paths or configuration limits. 

In Bash, a constant is simply a variable that you lock in place using the built-in readonly command. 

7. Write a shell script to read two integer numbers from the user and compute the sum of both the number. 

We use the read command to ask the user for input and the powerful arithmetic expansion $(( )) to handle the math: 

#!/bin/bash:Sum Two Numbers:sum_numbers.sh 
echo "Enter the first integer:" 
read NUM1 
 
echo "Enter the second integer:" 
read NUM2 
 
# Perform arithmetic calculation using $(( )) 
SUM=$((NUM1 + NUM2)) 
 
echo "The sum of $NUM1 and $NUM2 is: $SUM" 
 
 

8. What is the use of the source command in shell scripting? 

When you usually run a script (./script.sh), it opens its own little sandbox (a sub-shell). But if you source a script (or use the dot: .), you run it inside your current shell environment. 

Why this matters: This is vital when the script sets new environment variables (like updating your $PATH) or defines functions. If you just ran it normally, those changes would disappear when the script finished, but sourcing makes them stick around in your current session! 

9. How can you debug a shell script? Give two methods. 

Debugging is when you put on your detective hat to figure out why your script isn't doing what you told it to do! 

Method 1: The -x option (Execution Trace): 

This is like watching a step-by-step movie of your script running. You run it like this: bash -x ./my_script.sh 

Result: Bash will print every single command and its substituted variables, preceded by a + sign. This shows you exactly what the shell is trying to execute. 

Method 2: The -n option (Syntax Check): 

This is your quick grammar check. You run it like this: bash -n ./my_script.sh 

Result: Bash reads the commands but does not execute them. It's totally safe, and it just checks for fundamental syntax errors (like missing quotes or an unclosed if statement). 

10. Write a bash script to create and delete a file. 

This script uses the fundamental Linux commands for file management: touch to create the file and rm to safely remove it, with an if/then check for confirmation: 

#!/bin/bash:Create and Delete File:file_operations.sh 
FILE_NAME="temp_test_file.txt" 
 
echo "Attempting to create file: $FILE_NAME" 
# Command to create an empty file 
touch $FILE_NAME 
 
# Check if the file was created successfully 
if [ -f "$FILE_NAME" ]; then 
    echo "$FILE_NAME created successfully." 
else 
    echo "Error creating $FILE_NAME." 
    exit 1 
fi 
 
# Command to delete the file 
echo "Deleting file: $FILE_NAME" 
rm $FILE_NAME 
 
# Verify deletion 
if [ ! -f "$FILE_NAME" ]; then 
    echo "$FILE_NAME deleted successfully." 
else 
    echo "Error deleting $FILE_NAME." 
fi 
Assignment 7 

NAME- Shreya Rajni 

SECTION-3A 

ROLL NO.-59 

USN- ENG24CY0161 

 

1. What is a bash shell script? Give one example. 

A bash shell script is a text file that contains a series of commands that can be executed by the Linux shell automatically. 

Example: 

#!/bin/bash 

echo "This is my first shell script!" 

Shape 

2. Write a simple shell script to print “Hello World”. 

#!/bin/bash 

echo "Hello World" 

 Save as hello.sh and run: 

bash hello.sh 

Shape 

3. What is the purpose of comments (#) in a shell script? 

Comments help explain the code and are ignored by the shell during execution. 

Example: 

# This line prints a message 

echo "Hello" 

Shape 

4. How do you declare variables (int, float, double, string, Boolean, char) in a shell script? 

Bash treats all variables as strings, but they can be used as numbers too. 

int=10 

float=2.5 

double=5.55 

string="Hello" 

boolean=true 

char='A' 

Shape 

5. Write a shell script to display the current date and time. 

#!/bin/bash 

echo "Current Date and Time: $(date)" 

Shape 

6. Difference between a constant and a variable in bash script. 

Term 

Description 

Example 

Variable 

Value can change 

name="Komal" 

Constant 

Value cannot change (readonly) 

readonly pi=3.14 

Shape 

7. Script to read two integers and compute their sum. 

#!/bin/bash 

read -p "Enter first number: " a 

read -p "Enter second number: " b 

sum=$((a + b)) 

echo "Sum = $sum" 

Shape 

8. What is the use of source command in shell scripting? 

source runs a script in the current shell instead of starting a new one. 
Example: 

source file.sh 

Shape 

9. How can you debug a shell script? 

Two methods: 

Run with -x option → bash -x script.sh 

Add set -x inside the script to trace commands. 

Shape 

10. Write a bash script to create and delete a file. 

#!/bin/bash 

touch test.txt 

echo "File created" 

rm test.txt 

echo "File deleted" 

 Assignment 8 
NAME- Shreya Rajni 
SECTION-3A 
ROLL NO.-59 
USN- ENG24CY0161 
11. What is a user-defined function in shell scripting? 
A reusable block of code that performs a task. 
Example: 
myFunc() { 
echo "This is a user-defined function" 
} 
myFunc 
12. Bash script with a function to multiply two integers. 
#!/bin/bash 
multiply() { 
echo $(( $1 * $2 )) 
} 
multiply 5 6 
13. Explain how arrays (1D, 2D, 3D) are declared in bash scripting. 
• 1D Array: 
• arr=(10 20 30) 
• 2D (using nested arrays): 
Bash doesn’t support true 2D arrays, but you can simulate 
them: 
• matrix[0,0]=1 
• matrix[0,1]=2 
• 3D: Use associative arrays or files to emulate 3D data. 
14. Write a shell script to display elements of an array. 
#!/bin/bash 
arr=(apple banana cherry) 
for i in "${arr[@]}"; do 
echo $i 
done 
15. What is the purpose of cron in Linux? 
cron is used to schedule tasks automatically at specific intervals 
(e.g., backups, updates). 
16. Write a cron job to run a backup script every day at midnight. 
Edit crontab using: 
crontab -e 
Add this line: 
0 0 * * * /home/user/backup.sh 
17. How do you schedule a one-time job using at command? 
at 10:00 PM 
> bash backup.sh 
> <Ctrl+D> 
18. Write a script to display disk usage using df and du. 
#!/bin/bash 
echo "Disk Free:" 
df -h 
echo "Disk Usage:" 
du -h --max-depth=1 
19. How can you log the output of a script using the tee command? 
./myscript.sh | tee logfile.txt 
Displays output on screen and saves it in logfile.txt. 
20. Example of shell scripting automating system tasks. 
Example: Automatic Backup 
#!/bin/bash 
tar -czf backup_$(date +%F).tar.gz /home/user/documents 
echo "Backup done!"
>
Assignment 9 
NAME- Shreya Rajni 
SECTION-3A 
ROLL NO.-59 
USN- ENG24CY0161 
21. Script using if…else to check if a number is even or odd. 
#!/bin/bash 
read -p "Enter a number: " n 
if (( n % 2 == 0 )) 
then 
echo "Even" 
else 
echo "Odd" 
f
 i 
22. Difference between if and case statements. 
Feature if 
Use 
case 
For conditional comparisons For pattern matching 
Example if [ $a -gt 10 ]; then ... fi 
case $a in 1) ... ;; esac 
23. Script to find largest of three numbers. 
#!/bin/bash 
read -p "Enter three numbers: " a b c 
if ((a >= b && a >= c)) 
then echo "$a is largest" 
elif ((b >= c)) 
then echo "$b is largest" 
else 
echo "$c is largest" 
f
 i 
24. For loop to traverse an array. 
#!/bin/bash 
arr=(123 "Abs" -2.3 'A' 23.56 0) 
for val in "${arr[@]}" 
do 
echo $val 
done 
25. Script to display names of all files in current directory. 
#!/bin/bash 
for file in * 
do 
echo "$file" 
done 
26. Difference between while and until loops. 
Loop Condition Type Executes When 
while True 
until False 
Condition true 
Condition false 
27. Countdown timer script using while loop. 
#!/bin/bash 
count=5 
while [ $count -gt 0 ] 
do 
echo "$count" 
sleep 1 
((count--)) 
done 
echo "Time’s up!" 
28. Use of break and continue in loops. 
#!/bin/bash 
for i in {1..5} 
do 
if [ $i -eq 3 ]; then continue; fi 
if [ $i -eq 5 ]; then break; fi 
echo $i 
done 
29. Script to check if a file exists or not. 
#!/bin/bash 
read -p "Enter filename: " f 
if [ -e "$f" ]; then 
echo "File exists" 
else 
echo "File not found" 
f
 i 
30. Script to calculate factorial of a number using for loop. 
#!/bin/bash 
read -p "Enter number: " n 
fact=1 
for ((i=1;i<=n;i++)) 
do 
fact=$((fact*i)) 
done 
echo "Factorial = $fact"

