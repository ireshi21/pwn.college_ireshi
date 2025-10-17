# Forensics

## Challenge: Disk, disk, sleuth! II
### Solve 
All we know is the file with the flag is named `down-at-the-bottom.txt`... Disk image: dds2-alpine.flag.img.gz  
HInt: The sleuthkit has some great tools for this challenge as well.  

**Flag:** `picoCTF{f0r3ns1c4t0r_n0v1c3_db59daa5}`

METHOD:  
1. Use Autopsy tool and open the disc file
2. search for txt files
3. under txt files search down-at-the-bottom.txt
4. It has the flag  
   
