# Data Manipulation

## Challenge 1: Translating Characters


### Solve

**Flag:** `pwn.college{0xIJVBTeQtY0Tg-RD_mS-FyrZNV.01MxEzNxwyMwAzNzEzW}  `

```bash
hacker@data~translating-characters:~$ /challenge/run | tr ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ
yOUR CASE-SWAPPED FLAG:
pwn.college{0xIJVBTeQtY0Tg-RD_mS-FyrZNV.01MxEzNxwyMwAzNzEzW}

hacker@data~translating-characters:~$ /challenge/run | tr 'A-Za-z' 'a-zA-Z'
yOUR CASE-SWAPPED FLAG:
pwn.college{0xIJVBTeQtY0Tg-RD_mS-FyrZNV.01MxEzNxwyMwAzNzEzW}
```
### New Learnings

 tr translates the character provided in its first argument to the character provided in its second argument.   
ex- for PWN , tr P O
OWN  
It can also handle multiple characters, with the characters in different positions of the first argument replaced with associated characters in the second argument.   
hacker@dojo:~$ echo PWM.COLLAGE | tr MA NE  
PWN.COLLEGE  
  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Deleting Characters


### Solve

**Flag:** `pwn.college{sAwwn53PwelVyTqrlwwTNaILYUU.0FNxEzNxwyMwAzNzEzW}  `

```bash
hacker@data~deleting-characters:~$ /challenge/run | tr -d ^%
Your character-stuffed flag:
pwn.college{sAwwn53PwelVyTqrlwwTNaILYUU.0FNxEzNxwyMwAzNzEzW}
```
### New Learnings
-d flag and an argument of what characters to delete

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Deleting Newlines


### Solve

**Flag:** `pwn.college{Mj74Rb74r0IwphtZH23gGq_WXNz.0VNxEzNxwyMwAzNzEzW}`

```bash
hacker@data~deleting-newlines:~$ /challenge/run | tr -d '\n'
Your line-split flag: pwn.college{Mj74Rb74r0IwphtZH23gGq_WXNz.0VNxEzNxwyMwAzNzEzW}
```
### New Learnings
tr _ "\n" replaces underscores _ with newlines, splitting into separate lines.  
 
To represent special characters (like newline), you escape them with \.  

If you want to replace a literal backslash \, you must escape it twice \\.  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Extracting the first lines with head


### Solve

**Flag:** `pwn.college{YSvMoTCs4fKTMBI-KRGAlQb0PSB.0lNxEzNxwyMwAzNzEzW}`

```bash
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{YSvMoTCs4fKTMBI-KRGAlQb0PSB.0lNxEzNxwyMwAzNzEzW}
```
### New Learnings
hacker@dojo:~$ cat /something/very/long | head -n 2  
only head- shows the whole output  
here, first 2 lines  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 5: Extracting specific sections of text


### Solve

**Flag:** `pwn.college{gy0hmOkBrLQTer6p8JXOpLUGFoa.01NxEzNxwyMwAzNzEzW}`

```bash
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d " " -f 2 | tr -d "\n"
pwn.college{gy0hmOkBrLQTer6p8JXOpLUGFoa.01NxEzNxwyMwAzNzEzW}
```
### New Learnings
 cut -d " " -f 1 scores.txt  
The -d argument specifies the column delimiter (how columns are separated). In this case, it's a space character.  
The -f argument which column to extract as an arguement 

syntax: cut [delimiter][how columns are separated][-f which column to extract][filename(not compulsory)]

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Sorting Data


### Solve

**Flag:** `pwn.college{sB1cqzQhRml_TuF-IrDSssPlI20.0FM0MDOxwyMwAzNzEzW}`

```bash
hacker@data~sorting-data:~$ sort /challenge/flags.txt -r
pwn.college{sB1cqzQhRml_TuF-IrDSssPlI20.0FM0MDOxwyMwAzNzEzW}
```
### New Learnings
sort [filename][special arguement]
ARGUEMENTS:  
-r: reverse order (Z to A)  
-n: numeric sort (for numbers)  
-u: unique lines only (remove duplicates)  
-R: random order!  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------
