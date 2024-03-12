# picoCTF_gym by Liza Kim
## General Skills
### Python Wrangling | 10 points
   
We are given three files: a python script, a password, and a flag. The task asks us to run the script and use the given password to get the flag within the flag file.

1. I first used the given YouTube video to create a directory for this challenge.
2. I then used wget to place the three given files into my pythonwrangling directory.
3. I followed picoCTF's second clue, which was to use man python to check out python commands, but I didn't really understand which one to use so I quit out of the manual and ran python ende.py. The output said I could use "python ende.py (-e/-d) [file]", which I assumed meant I could run the command I ran previously but with either an -e or -d followed by the file I wanted.
4. So I first tried -e and ran "python ende.py -e pw.txt", but then I was asked for the password, which made me realize I probably should have used the file.txt.en file with the -e command instead of the password file.
5. So I tried again (python ende.py -e file.txt.en), entered the password from the txt.file (I ended up just manually opening it and copy/pasting the password), and got a bunch of gibberish that was not formatted in the expected way (picoCTF{FLAG}).
6. So I did the same process again but using "python ende.py -d file.txt.en" and got the answer (picoCTF{4p0110_1n_7h3_h0us3_192ee2db}).    


### Wave a flag | 10 points

We are given a program that will output the flag for us. We are to make it executable, execute it, and use the help commands to figure out what the program has to offer. 

1. Downloaded the given program named "warm". Checked it out, all gibberish. Looked through the five hints from picoCTF.
2. One of the clues was to use the command "chmod +x warm". I looked up what chmod +x is supposed to do and found my answer here: https://shorturl.at/ilyPT
3. Created a waveaflag directory and used wget to place the given program into it.
4. Followed the clue saying I should run "chmod +x warm" before using "./warm".
5. Received a message to use -h after running "./warm". Ran "./warm -h" and received message with the answer (picoCTF{b1scu1ts_4nd_gr4vy_616f7182}).


### Nice netcat... | 15 points

We are given a netcat command to run in the terminal and decipher it's non-English language in order to find the flag. 

1. Didn't create a directory since there aren't any files involved. Checked out the hints and realized there would be ASCII translation.
2. Ran the given command (nc mercury.picoctf.net 7449) and received a list of numbers, which I assumed was ASCII.
3. Pulled up an ASCII to text translator. The first one I pulled up did a bad job translating the numbers, but the second one produced a legible message, which was the answer (picoCTF{g00d_k1tty!_n1c3_k1tty!_f2d7cafa}).


### Static ain't always noise | 20 points

We're supposed to look into a binary file called 'static' with the help of a BASH script in order to find the flag. 

1. No hints sadness. Looked through the bash script to understand what it's supposed to do, found hints there. Looked through Linux notes to understand the first two lines. It seems the script takes the first file given to it, picks out the text, and prints the text into a new text file.
2. Created a new directory called staticaintalwaysnoise and placed the binary file and the bash file into it.
3. Ran static to see what's inside of it using "./static". Didn't work, remembered I need to use "chmod +x static" first. After doing so, I got a messsage saying the flag was somewhere in the static file.
4. Ran shell file with static as argument using "source ltdis.sh static". Found ways to run shell file from here: https://shorturl.at/HIN67
5. Received message that static was disassembled and assembled into a new file, and it also created a file with only strings from static.
6. Decided to use "cat" to look into the second file, since the flag would likely be a string.
7. Scrolled through the items and found the answer (picoCTF{d15a5m_t34s3r_f5aeda17}) at position 1020.


### Tab, Tab, Attack | 20 points

We're supposed to use the tab button to make our navigation of a deep and lengthy-named directory easier. In the end, there's a content file, but we need to get to it first. 

1. Downloaded zip folder, looked through it, ridiculous. Read hint about using tab to autocomplte. Created tabtabattack directory to place the folder into.
2. Unzipped folder by using "unzip [tab]" to autocomplete the name of the folder. Searched for "how to unzip a file in linux terminal" and just tried the first command I found.
3. Used "cd [tab]/[tab]/[tab]/[tab]/[tab]/[tab]/[tab]" to enter the directory with the content file
4. Used "cat [tab]" to get the open the file. Got a bunch of gibberish, but amongst the gibberish was the answer (picoCTF{l3v3l_up!_t4k3_4_r35t!_6f332f10}).


### Magikarp Ground Mission
1. 
