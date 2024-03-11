# picoCTF_gym
## by Liza Kim
### General Skills
Python Wrangling | 10 points
   
   We are given three files: a python script, a password, and a flag. The task asks us to run the script and use the given password to get the flag within the flag file.

   I first used the given YouTube video to create a directory for this challenge. I then used wget to place the three given files into my pythonwrangling directory.
   I followed picoCTF's second clue, which was to use man python to check out python commands, but I didn't really understand which one to use so I quit out of the manual and ran python ende.py. The output said I could use "python ende.py (-e/-d) [file]", which I assumed meant I could run the command I ran previously but with either an -e or -d followed by the file I wanted. So I first tried -e and ran "python ende.py -e pw.txt", but then I was asked for the password, which made me realize I probably should have used the file.txt.en file with the -e command instead of the password file. So I tried again (python ende.py -e file.txt.en), entered the password from the txt.file (I ended up just manually opening it and copy/pasting the password), and got a bunch of gibberish that was not formatted in the expected way (picoCTF{FLAG}). So I did the same process again but using "python ende.py -d file.txt.en" and got the answer (picoCTF{4p0110_1n_7h3_h0us3_192ee2db}).    
