# BASH in data science
The free and open source version of Unix for personal computers is called Linux. We are interested in using the shell program called BASH (Bourne Again Shell) that communicates user commands to the computer to execute them. BASH has many light-weight and easy to use tools for analyzing and organizing data that could be useful to you in your data science work. BASH and Linux are also commonly used by data scientistsand engineers. For this reason, it is also helpful to understand these programs as univeristy professionals who will need to interact with technical data expersts to ensure we can effectively understand and communicate on Linux related topics when it is part of the tech stack in use.
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

### Searching & Help
- `find . -name "file.txt"` – Searches for a file named "file.txt" in the current folder.  
- `history` – Displays previously run commands.  
- `man pwd` – Shows the help manual for any command.  

## Tutorial
The tutorial below incorporates parts of the tutorial from the text as well as some additional elements.

### Navigation and data import
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
4. `grep 'Engineering' *.txt' - Searches all txt files in the directory telling us which files contain students with Engineering majors and shows us the row entries.
5. `grep "Engineering" *.txt | tr '\t' ',' > results.csv` - Outputs all of the engineering students to a csv file. Tr (translate) is replacing the tabs with commas.
6. `cat a_student_list.txt | cut -f 3` - Pipes (|) the cat command over to the cut command to give us only the list of majors (-f 3 means column 3) for inspection.
8. `cat *.txt | cut -f 3 | sort | uniq -c` - Displays the unique values in the third column for all txt files in the directory and counts them.
9. 
