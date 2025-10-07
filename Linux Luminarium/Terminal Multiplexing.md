# Terminal Multiplexing

## Challenge 1: Launching Screen


### Solve

**Flag:** `pwn.college{oLWa2s5qf_fJX1VQ_KsRVhj6U0Y.0VN4IDOxwyMwAzNzEzW}`
change ownership and read the flag

```bash
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{oLWa2s5qf_fJX1VQ_KsRVhj6U0Y.0VN4IDOxwyMwAzNzEzW}
```
### New Learnings

screen is a program that creates virtual terminals inside your terminal.  
 type exit or press Ctrl-D to leave the screen session. Then screen will terminate and return you to your original shell.  



### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Detaching and Attaching


### Solve

**Flag:** `pwn.college{MS8_mRzC9lKhB9eqAlYG79yIOL9.0lN4IDOxwyMwAzNzEzW}`

When in screen, Ctrl+A, then release both and press d to detach.    

```bash
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen
[detached from 147.pts-0.terminal-multiplexing~detaching-and-attaching]
hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 147.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:

  screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
[detached from 147.pts-0.terminal-multiplexing~detaching-and-attaching]


hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{MS8_mRzC9lKhB9eqAlYG79yIOL9.0lN4IDOxwyMwAzNzEzW}
Yes! Flag is: pwn.college{MS8_mRzC9lKhB9eqAlYG79yIOL9.0lN4IDOxwyMwAzNzEzW}
```
### New Learnings

1. You detach by pressing Ctrl-A, followed by d (for detach). This leaves your session running in the background while you return to your normal terminal.  
2. To reattach, you can use the -r argument to screen:  hacker@dojo:~$ screen -r  
3. Ctrl-A is screen's activation key for all of its shortcuts in its default configuration. All screen functionality is activated by some command combination starting with Ctrl-A.  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Finding Sessions

### Solve

**Flag:** `pwn.college{k9ekD2OVdvUQC1pdPgX7QwHd1Fz.01N4IDOxwyMwAzNzEzW`

```bash
hacker@terminal-multiplexing~finding-sessions:~$  echo 'Congratulations! You found the right session!'
Congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{k9ekD2OVdvUQC1pdPgX7QwHd1Fz.01N4IDOxwyMwAzNzEzW}
pwn.college{k9ekD2OVdvUQC1pdPgX7QwHd1Fz.01N4IDOxwyMwAzNzEzW
```
### New Learnings

1. screen -ls for list of running sessions.  
23855.morework    (Detached)  [PID.screenname]  
2. To attach to a specific one, you use its name or its PID by giving it as an argument to screen -r [PID or ScreenName]  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Switching Windows


### Solve

**Flag:** `pwn.college{AsQ1ZrWYmWB6Mhicg7JeIDl1TG9.0FO4IDOxwyMwAzNzEzW}`

attach to screen with screen -r  
ctrl+A and then 0 to get to window 0  

```bash
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{AsQ1ZrWYmWB6Mhicg7JeIDl1TG9.0FO4IDOxwyMwAzNzEzW}
> MSG
```
### New Learnings

1. Windows in a screen are handled with different keyboard shortcuts, all starting with Ctrl-A:  

Ctrl-A c - Create a new window  
Ctrl-A n - Next window  
Ctrl-A p - Previous window  
(Ctrl-A 0 through Ctrl-A 9) - Jump directly to window 0-9  
Ctrl-A " - bring up a selection menu of all of the windows  

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------


## Challenge 5: Detaching and Attaching (tmux)

### Solve

**Flag:** `pwn.college{QG_8RoAlYZTpXpqDsLTZs_HwsAk.0VO4IDOxwyMwAzNzEzW}`

```bash
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
  tmux attach

You'll find the flag waiting for you there!

hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$  echo Congratulations, here is your flag: pwn.college{QG_8RoAlYZTpXpqDsLTZs_HwsAk.0VO4IDOxwyMwAzNzEzW}
```
### New Learnings
 1. tmux (terminal multiplexer) does all the same things but tmux uses Ctrl-B as its command prefix.  
 2. So to detach from tmux, you press Ctrl-B followed by d  
 3. tmux ls - List sessions  
tmux attach or tmux a - Reattach to session  
4. tmux also has a status bar.  
5. diference between screen and tmux: tmux offers a more modern interface and a richer set of features which are particularly useful for power users who need more control over their environments  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 6: Switching Windows (tmux)


### Solve

**Flag:** `pwn.college{UZ_GZB1LX_UAfqkV3nNIH3t39iS.0FM5IDOxwyMwAzNzEzW}`

```bash
hacker@terminal-multiplexing~switching-windows-tmux:~$  cat <<MSG
> Excellent work! You found window 0!
> Here is your flag: pwn.college{UZ_GZB1LX_UAfqkV3nNIH3t39iS.0FM5IDOxwyMwAzNzEzW}
> MSG
```
### New Learnings

1. Ctrl-B c - Create a new window  
Ctrl-B n - Next window  
Ctrl-B p - Previous window  
(Ctrl-B 0 through Ctrl-B 9) - Jump to window 0-9  
Ctrl-B w - See a nice window picker  

2. Tmux shows your windows at the bottom in a status bar that looks like:  

[0] 0:bash* 1:bash  
The * shows your current window  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------
