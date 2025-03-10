# BASH in data science
The free and open source version of Unix for personal computers is called Linux. We are interested in using the shell program called BASH (Bourne Again Shell) that communicates user commands to the computer to execute them. BASH has many light-weight and easy to use tools for analyzing and organizing data that could be useful to you in your data science work as higher ed experts. BASH and Linux are also commonly used by data scientists and engineers. For this reason, it is also helpful to understand these programs as professionals who will need to interact with technical data experts to ensure you can effectively understand and communicate on Linux related topics when it is part of the tech stack in use.
## Accessing Linux 
### Mac
If you are on a Mac you can access BASH (Born Again Shell) by typing:
`command+space` and then searching for `terminal`.
### PC
If you are on a PC accessing bash is a bit more challenging but certainly achievable. I found the instructions in the text to be inadequate so [I created my own here](https://tennesseetechuniversity-my.sharepoint.com/:p:/g/personal/mlittrell_tntech_edu/EW-ikoZA5zVLvd3ueLH-TOoBl5SIqtIwn2AZeZJUxtH6kQ?e=cqpPZS). An important note: You will need Admin Access to your PC to be able to follow these instructions.
## Basic Commands
These basic commands are meant to supplment what is seen in the text. There is overlap but some additional ones too.

### Navigation Commands
- `ls` – Lists files and folders in the current directory.  
- `ls -l` – Shows file details (size, date, permissions).  
- `cd /example/path/documents` – Changes working directory.  
- `cd ..` – Moves up one directory level.  
- `cd ~` – Returns to the home directory.  

### File Management
- `touch file.txt` – Creates a new empty file.  
- `cp file1.txt file2.txt` – Copies a file.  
- `mv file.txt folder/` – Moves a file to a folder.  
- `mv oldname.txt newname.txt` – Renames a file.  
- `rm file.txt` – Deletes a file.  
- `rmdir folderName` – Deletes an empty directory.  

### File Exploration
- `cat file.txt` – Displays the content of a file.  
- `head file.txt` – Shows the first 10 lines of a file.  
- `tail file.txt` – Shows the last 10 lines of a file.  
- `grep "word" file.txt` – Finds lines containing "word" in a file.  
- `sort file.txt` – Sorts text alphabetically.  
- `sort numbers.txt` – Sorts numbers in order.
- `awk` - Searches text for specified patterns.

### Searching & Help
- `find . -name "file.txt"` – Searches for a file named "file.txt" in the current folder.  
- `history` – Displays previously run commands.  
- `man pwd` – Shows the help manual for any command.  

## Tutorial 1: Navigation and file manipulation
The tutorial below incorporates parts of the tutorial from the text as well as some additional elements.

### Navigation and data creation
From the BASH prompt:
1. `mkdir university_data` - Create a directory called university_data.
2. `cd university_data` - Changes the working directory to univeristy_data.
3. `touch a_student_list.txt` - Creates the text file a_student_list.
4. `touch b_student_list.txt` - Creates the text file b_student_list.
5. `ls` - Shows the contents of the directory with the newly created files.
6. `nano a_student_list.txt` - Opens student_list in the Nano text editor.
7. Copy and paste the Students majors list A (found below) into Nano.
8. `Ctrl+o`, then `enter`, then `ctrl+x` - Saves the pasted text to the file and exits Nano.
9. `touch b_student_list.txt` - This creates another blank list to give context to our later commands.
10. Copy and paste the Students majors list B (found below) into your Nano.
11. `Ctrl+o`, then `enter`, then `ctrl+x` - Saves the pasted text to the file and exits Nano.

### Student majors list A
Note: This list is seperated by tabs which is the default delimeter for many BASH commands. So copy and paste all of the data exactly as is.
```
John	Adams	Computer Science  
Emma	Anderson	Biology  
Liam	Archer	Psychology  
Olivia	Abbott	Business  
Noah	Ashton	Engineering  
Ava	Aldridge	Computer Science  
William	Atkinson	Biology  
Sophia	Armstrong	Psychology  
James	Adler	Business  
Isabella	Augustine	Engineering  
Benjamin	Alston	Computer Science  
Mia	Abrams	Biology  
Elijah	Ashford	Psychology  
Charlotte	Ainsworth	Business  
Mason	Ackerman	Engineering  
Amelia	Abernathy	Computer Science  
Lucas	Arnett	Biology  
Harper	Astor	Psychology  
Henry	Alden	Business  
Evelyn	Arrington	Engineering   
```
### Student majors list B
Note: This list is seperated by tabs which is the default delimeter for many BASH commands. So copy and paste all of the data exactly as is.
```
Ethan	Brooks	Computer Science  
Lily	Bennett	Business  
Jackson	Baldwin	Engineering  
Grace	Bishop	Psychology  
Carter	Boone	Biology  
Scarlett	Baxter	Computer Science  
Owen	Bradford	Business  
Hannah	Bryant	Psychology  
Levi	Burton	Biology  
Zoe	Benson	Engineering  
Nathan	Barrett	Computer Science  
Aubrey	Browning	Business  
Julian	Bond	Psychology  
Victoria	Blackwell	Biology  
Wyatt	Brennan	Engineering  
Ellie	Buchanan	Computer Science  
Miles	Boyer	Computer Science  
Natalie	Blevins	Psychology  
Gabriel	Barton	Biology  
Stella	Bowman	Engineering  
```

### Examining the data
1. `cat a_student_list.txt` - Outputs the file contents to the terminal.
2. `head a_student_list.txt` - Outputs the first 10 lines of the file to the terminal.
3. `less a_student_list.txt` - Outputs the file contents without clogging the terminal. `q` to exit.
4. `grep 'Engineering' *.txt` - Searches all txt files in the directory telling us which files contain students with Engineering majors and shows us the row entries.
5. `grep "Engineering" *.txt | tr '\t' ',' > results.csv` - Outputs all of the engineering students to a csv file. Tr (translate) is replacing the tabs with commas.
6. `cat a_student_list.txt | cut -f 3` - Pipes (|) the cat command over to the cut command to give us only the list of majors (-f 3 means column 3) for inspection.
8. `cat *.txt | cut -f 3 | sort | uniq -c` - Displays the unique values in the third column for all txt files in the directory and counts them.

## Tutorial 2: Exploration and simple analysis
Scenario: You are a university professional who has been provided some data from your course management software (iLearn) with the open ended goal of exploring the data to understand student engagement with iLearn courses.

- student_id - Unique ID for each student
- course_id - Unique ID for the course
- department - Department offering the course
- logins - Number of times the student logged in
- videos_watched - Number of lecture videos watched
- assignments_completed - Number of assignments completed
- forum_posts - Number of discussion forum posts
- final_grade - Final grade as a percentage

### Import the data:
To work with the data(student_engagement.csv), download it [here](https://tennesseetechuniversity-my.sharepoint.com/:x:/g/personal/mlittrell_tntech_edu/EcFLuxTfjAFGhVHUbuDKH5cBo1FSe06cihwq-gK4u4YWcw?e=vs8zLR) and use your OS to drag and drop it into your folder university_data.

The columns for this data are:

1. `cd university_data` - Changes your current directory to the previously created univeristy_data directory.
2. `cut -d ',' -f3 student_engagement.csv | sort | uniq -c` - Outputs the number of students in each department.
- cut -d ',' -f3 - extracts the department column (column c) specifying commas (instead of the default tab) for the delimiter.
- sort - orders the department names.
- uniq -c - counts how many times each unique department name appears.
3. `awk -F ',' '$3 == "Business" && $8 >= 80' student_engagement.csv | wc -l` - Counts the number of business students who also scored 80 or above on their final grade.
- -F ',' tells awk to use a comma as the delimiter.
- $3 == "Business" - filters rows where the department (column 3) is "Business."
- $8 >= 80 - filters rows where the final grade (column 8) is 80 or above.
- | wc -l = counts how many rows match both conditions.
4. `cut -d ',' -f3 student_engagement.csv | sort | uniq -c | sort -n` - Counts the number of students in each department and lists the counts in ascending order.
- cut -d ',' -f3 - Extracts the department column (column 3).
- sort - Sorts the department names.
- uniq -c - Counts occurrences of each department.
- sort -n - Sorts the counts in ascending order.
5. `awk -F ',' '$4 > 30 {print $3}' student_engagement.csv | sort | uniq -c | sort -nr | head -3` - Counts students who logged in more than 30 times and lists the top three departments for which this contdition was true.
- awk -F ',' '$4 > 30 {print $3}' - Filters students with more than 30 logins and prints their department (column 3).
- sort - Sorts the department names.
- uniq -c - Counts occurrences of each department.
- sort -nr - Sorts the counts in descending order.
- head -3 - Displays only the top 3 departments.

## Chapter 4 Assignment:
Continue working with the student_engagment.csv data to answer further questions about the topic. Answer the following questions by including the command that you entered and a screen shot (using Snipping Tool, Greenshots, etc.) of the output. Helpful for this assignment could be the man command (example `man awk`) and generative AI for direction.
### Questions to answer:
1. Identify students who have a failing final grade below 70.
2. Find the number of students with more than 10 logins.
3. Find the top 5 students in terms of forum post count and output the results to a new file called top_5.csv.
4. Find the students who only completed 1 assignment.
5. Find the students who completed less than 3 assignments and also had a grade of 70 or less.
6. Copy the student_engagment.csv data set to a new file called student_engagment_2.csv and count how many engineering students are now in both files collectively.
7. Delete the newly created student_engagment_2.csv file.


