# Untangling Users

## Challenge 1: Becoming root with su


### Solve

**Flag:** `pwn.college{sC1ybEQJY6dcTHnTWIq6ali2CGT.QX1UDN1wyMwAzNzEzW}`

```bash
hacker@users~becoming-root-with-su:~$ su
Password: 
root@users~becoming-root-with-su:/home/hacker# cat /flag
pwn.college{sC1ybEQJY6dcTHnTWIq6ali2CGT.QX1UDN1wyMwAzNzEzW}
```
### New Learnings

1. su runs as root  
2. before setting user as root, it requires the root password  

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 2: Other users with su


### Solve

**Flag:** `pwn.college{cfp-LossU-Bqaph2UP0lVerF3JL.QX2UDN1wyMwAzNzEzW}`

```bash
hacker@users~other-users-with-su:~$ su zardus
Password: 
zardus@users~other-users-with-su:/home/hacker$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{cfp-LossU-Bqaph2UP0lVerF3JL.QX2UDN1wyMwAzNzEzW}
```
### New Learnings

1. you can specify which user you wish to change to by  
su [user-name]  


  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 3: Cracking passwords

### Solve

**Flag:** `pwn.college{42RE_aIg4ku-rpNUXrcvKlnCBaF.QX3UDN1wyMwAzNzEzW}`

```bash
hacker@users~cracking-passwords:/challenge$ john ./shadow-leak
Loaded 1 password hash (crypt, generic crypt(3) [?/64])
Press 'q' or Ctrl-C to abort, almost any other key for status
aardvark         (zardus)
1g 0:00:00:20 100% 2/3 0.04835g/s 281.5p/s 281.5c/s 281.5C/s Johnson..buzz
Use the "--show" option to display all of the cracked passwords reliably
Session completed
hacker@users~cracking-passwords:/$ su zardus
Password: 
zardus@users~cracking-passwords:/$ /challenge/run
Congratulations, you have become Zardus! Here is your flag:
pwn.college{42RE_aIg4ku-rpNUXrcvKlnCBaF.QX3UDN1wyMwAzNzEzW}
```
### New Learnings

/etc/shadow stores user password hashes (not plain text).  

Each line is colon-separated; field 1 = username, field 2 = password/hash.  

* or ! in the password field = password login disabled for that account.  

A blank password field = no password (bad misconfiguration; allows password-less su in some setups).  

Long strings like $6$...$... are hashed passwords.    

su hashes your typed password and compares it to the stored hash, match = access granted.  

If an attacker obtains /etc/shadow, they can attempt to crack hashes offline (common leak risk).  

  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------

## Challenge 4: Using sudo


### Solve

**Flag:** `pwn.college{ABR1UdIi63mNG_-64XQ6k8NJMcs.QX4UDN1wyMwAzNzEzW}`

```bash
hacker@users~using-sudo:~$ whoami
hacker
hacker@users~using-sudo:~$ sudo whoami
root
hacker@users~using-sudo:~$ cat /flag
cat: /flag: Permission denied
hacker@users~using-sudo:~$ sudo cat /flag
pwn.college{ABR1UdIi63mNG_-64XQ6k8NJMcs.QX4UDN1wyMwAzNzEzW}
```
### New Learnings

1. Admin access shifted from su to sudo because root passwords are hard to manage and leak-prone.  
2. su launches a shell as another user and traditionally relied on knowing the root password.  

sudo runs a single command as root by default, using policy rules instead of a shared root password.  

Example: whoami - your user, sudo whoami- root.  


  

### References

Challenge description.

# ----------------------------------------------------------------------------------------------------------