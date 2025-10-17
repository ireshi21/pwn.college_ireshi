# Forensics

## Challenge: Secret of the Polyglot
### Solve 
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is.  
They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file? 

**Flag:** `picoCTF{f1u3n7_1n_pn9_&_pdf_53b741d6}`

METHOD:  
1. Open file in metadata- shows PNG file  
2. Open as PNG file (just open with any browser) - shows the second half of the flag  
3. Open pdf file in hex editor- shows PNG first
4. search where PDF starts- until then copy the hex codes- save the file in your computer
5. open it and see the first half of the flag  
