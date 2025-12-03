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

