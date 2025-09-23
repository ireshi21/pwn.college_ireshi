# Comprehending Commands

## Challenge 1: cat: not the pet, but the command!

### Solve
**Flag:** `pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}`

```bash
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag
pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}
hacker@commands~cat-not-the-pet-but-the-command:~$ cat flag flag
pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}
pwn.college{4VLiRz7dPhg0-h5QtIDZOQ4MlbG.QXxcTN0wyMwAzNzEzW}
```
### New Learnings

1. `cat` is most often used for reading out files  
2. cat will concatenate (hence the name) multiple files if provided multiple arguments  
3.  if you give no arguments at all, cat will read from the terminal input and output it



### References

Challenge description and geekforgeeks.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: catting absolute paths

### Solve
**Flag:** `pwn.college{gJw0r3pc64QEVE0VHUjImMmb8UO.QX5ETO0wyMwAzNzEzW}`

```bash
hacker@commands~catting-absolute-paths:~$ cat /flag
pwn.college{gJw0r3pc64QEVE0VHUjImMmb8UO.QX5ETO0wyMwAzNzEzW}
```
### New Learnings

1.  cat's arguments can be described as absolute paths  

eg: hacker@dojo:~$ cat /challenge/DESCRIPTION.md  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: more-catting-practice

### Solve
**Flag:** `pwn.college{QxoeOWH64EX-R4uEC-NzHXggV0D.QXwITO0wyMwAzNzEzW}`

```bash
hacker@commands~more-catting-practice:~$ cat /usr/lib/ipxe/flag
pwn.college{QxoeOWH64EX-R4uEC-NzHXggV0D.QXwITO0wyMwAzNzEzW}
```
### New Learnings

1.  cat can read a file directly by specifying it's absolute path

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: grepping-for-a-needle-in-a-haystack

### Solve
**Flag:** `pwn.college{UtRCBjrCNE1bzuZsIFNWd1GMO1n.QX3EDO0wyMwAzNzEzW}`

```bash
hacker@commands~grepping-for-a-needle-in-a-haystack:~$ grep -n  pwn.college /challenge/data.txt
72378:pwn.college{UtRCBjrCNE1bzuZsIFNWd1GMO1n.QX3EDO0wyMwAzNzEzW}
```
### New Learnings

1.  GREP  
hacker@dojo:~$ grep SEARCH_STRING /path/to/file  
-i or --ignore-case: Ignores case distinctions when matching the pattern.  
-v or --invert-match: Selects lines that do not match the pattern.  
-n or --line-number: Prints the line number along with the matching line.  
-c or --count: Prints only a count of the matching lines, not the lines themselves.  
-l or --files-with-matches: Prints only the names of files containing matches, not the matching lines.  
-r or --recursive: Searches recursively through directories.  

### References

Challenge description and geekforgeeks.

# ----------------------------------------------------------------------------------------------------------

## Challenge 5: comparing files

### Solve
**Flag:** `pwn.college{Yx_VhhfWk2ovuo-_s__-MM04GK6.01MwMDOxwyMwAzNzEzW}`

```bash
hacker@commands~comparing-files:~$ cd /challenge
hacker@commands~comparing-files:/challenge$ diff decoys_only.txt decoys_and_real.txt
60a61
> pwn.college{Yx_VhhfWk2ovuo-_s__-MM04GK6.01MwMDOxwyMwAzNzEzW}
```
### New Learnings

1. diff compares two files line by line and shows you exactly what's different between them.  
1a2 means "after line 1 of file1, add line 2 of file2"  
line 2 changed (2c2) 


### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: listing files

### Solve
**Flag:** `pwn.college{IRU7u6vWgSIYywZSEj0HYNmYcNX.QX4IDO0wyMwAzNzEzW}`

```bash
hacker@commands~listing-files:/challenge$ ls /challenge
18701-renamed-run-3303  DESCRIPTION.md
hacker@commands~listing-files:/challenge$ cat 18701-renamed-run-3303
#!/opt/pwn.college/bash
echo "Yahaha, you found me! Here is your flag:"
cat /flag
hacker@commands~listing-files:/challenge$ /challenge/18701-renamed-run-3303 ~/flag
Yahaha, you found me! Here is your flag:
pwn.college{IRU7u6vWgSIYywZSEj0HYNmYcNX.QX4IDO0wyMwAzNzEzW}
```
### New Learnings

1. ls will list files in all the directories provided to it as arguments, and in the current directory if no arguments are provided  
2. cat reads contents of the file, absolute path runs the file which has instructions for the computer  (for ex, running flag)
3. /challenge/18701-renamed-run-3303 ~/flag explained
 
/challenge/18701-renamed-run-3303  

The program/executable you are running.  

Absolute path ensures Linux knows exactly where it is.  

Has permission to read the protected /flag file.  
  
~/flag : argument to the program  

~ expands to your home directory (/home/hacker).  

Instructs the program where to write the flag.  
 
What happens when you run it:  

The program reads /flag (hidden/protected).  

Writes its contents to /home/hacker/flag.  


### References

Challenge description and GPT to clear doubts.