# Unix in data science
The free and open source version of Unix for personal computers is called Linux. It has many light-weight and easy to use tools for analyzing and organizing data that could be useful to you in your data science work.
## Accessing Linux 
### Mac
If you are on a Mac you can access BASH (Born Again Shell) by typing:
`command+space` and then searching for `terminal`.
### PC
If you are on a PC accessing bash is a bit more challenging but certainly achievable. I found the instructions in the text to be inadequate so [I created my own here](https://tennesseetechuniversity-my.sharepoint.com/:p:/g/personal/mlittrell_tntech_edu/EW-ikoZA5zVLvd3ueLH-TOoBl5SIqtIwn2AZeZJUxtH6kQ?e=cqpPZS). An important note: You will need Admin Access to your PC to be able to follow these instructions.
## Basic Commands
These basic commands are meant to supplment what is seen in the text. There is overlap but some additional ones too.

1. `ls` – Lists files and folders in the current directory.
2. `ls -l` – Shows file details (size, date, permissions).
3. `find . -name "file.txt"` – Searches for a file named "file.txt" in the current folder.
4. `grep "word" file.txt` – Finds lines containing "word" in a file.
5. `touch file.txt` – Creates a new empty file.
6. `cat file.txt` – Displays the content of a file.
7. `head file.txt` – Shows the first 10 lines of a file.
8. `tail file.txt` – Shows the last 10 lines of a file.
9. `cp file1.txt file2.txt` – Copies a file.
10. `mv file.txt folder/` – Moves a file to a folder.
11. `mv oldname.txt newname.txt` – Renames a file.
12. `rm file.txt` - Deletes a files.
13. `rmdir folderName` - Deletes a directory.
14. `cd /example/path/documents` - Changes working directory that you are currently located in
15. `cd ..` - Changes the working directory to the level before it.
16. `cd ~` - Returns you to the home directory from anywhere.
17. `history` - See all previously run commands.
18. `man pwd` - Shows the help manual for any command.
19. `sort file.txt` - Sorts text alphabetically.
20. `sorts numbers.txt` - Sorts numbers in order.

## Tutorial
The tutorial below incorporates parts of the tutorial from the text as well as some additional elements.

From the BASH prompt:
1. `mkdir university_data` - Create a directory called university_data.
2. `cd university_data` - Changes the working directory to univeristy_data.
3. `touch student_list.txt` - Creates the text file student_list.
4. `ls` - Shows the contents of the directory with the newly created file.
5. `nano student_list.txt` - Opens student_list in the Nano text editor.
6. Copy and paste the [Student List Data](https://github.com/mlittrell-ttu/HRED-7160/blob/main/Chapter%204:%20Unix.md#tutorial) into your Nano.
7. `Ctrl+O`, then `enter`, then `ctrl+x` - Saves the pasted text to the student_list file.
### Student List Data
```
John       Smith       3.2
Emma       Johnson     3.8
Liam       Williams    2.5
Olivia     Brown       3.9
Noah       Jones       2.1
Ava        Garcia      3.4
William    Miller      2.9
Sophia     Davis       3.7
James      Rodriguez   1.8
Isabella   Martinez    3.5
Benjamin   Hernandez   2.2
Mia        Lopez       3.6
Elijah     Gonzalez    3.1
Charlotte  Wilson      2.7
Mason      Anderson    3.0
Amelia     Thomas      3.3
Lucas      Taylor      1.9
Harper     Moore       2.6
Henry      Jackson     4.0
Evelyn     Martin      1.5
```
