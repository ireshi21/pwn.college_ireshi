# Forensics

## Challenge: Torrent Analyzer
### Solve 
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is.  
They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? 

**Flag:** `picoCTF{ubuntu-19.10-desktop-amd64.iso}`

METHOD:  
1. open file in wireshark  
2. search bt-dht files by filter  
3. double click on info column  
4. info_peers has a most repeating info_hash
5. copy paste in linuxtracker.org 
6. says in the hint- files ends with .iso
   

### References  
https://www.techworm.net/2017/03/seeds-peers-leechers-torrents-language.html  
