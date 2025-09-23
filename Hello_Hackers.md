# Hello Hackers

## Challenge 1: Intro to commands

### Solve
**Flag:** `pwn.college{EQubdgVexOmVoRHtqJyLgnL3GDj.QX3YjM1wyMwAzNzEzW}`

```bash
hacker@hellointro-to-commands:$ whoami
hacker
hacker@hellointro-to-commands:$ hello
Success! Here is your flag:
pwn.college{EQubdgVexOmVoRHtqJyLgnL3GDj.QX3YjM1wyMwAzNzEzW}
```
### New Learnings
whoami command: gives the username of the user running the terminal
here, hacker means a low privilege user who doesn't have root access yet and tries to escalate to root

Linux is case sensitive- hello and HELLO are not the same

### References

ChatGPT to understand the theoretical part.

# ----------------------------------------------------------------------------------------------------------



## Challenge 2: Intro to arguments

### Solve
**Flag:** `pwn.college{U89LfcVyzPVRGWQYFRwcbDYSj5s.QX4YjM1wyMwAzNzEzW}`

hello command with hackers argument

```bash
hacker@hello~intro-to-arguments:~$ hello hackers
Success! Here is your flag:
pwn.college{U89LfcVyzPVRGWQYFRwcbDYSj5s.QX4YjM1wyMwAzNzEzW}
hacker@hello~intro-to-arguments:~$ 
```

### New Learnings

1.echo is a command which gives back whatever user types in the terminal.

2.hacker@dojo:`~$`
-hacker is username 
-dojo is the hostname of the machine the shell is on
-"$" means that hacker is NOT an administrative user
-"#" means that it is an administrative user

### References

Info given in the challenge description.
# ----------------------------------------------------------------------------------------------------------



## Challenge 3: Command History

### Solve
**Flag:** `pwn.college{ssCyliAdrECkEPHvYgwGKe7J6gL.0lNzEzNxwyMwAzNzEzW}`

The shell saves a history of every command invoked. Clicking the up arrow button gives the commands. 

```bash
hacker@hellocommand-history:$ the flag is pwn.college{ssCyliAdrECkEPHvYgwGKe7J6gL.0lNzEzNxwyMwAzNzEzW}

```

### New Learnings

All the command history is saved in the shell.

### References

Info given in the challenge description.
