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


### Magikarp Ground Mission | 30 points

We're supposed to run an instance of the shell, sign into it using given credentials, and look through the directories/files to find the picoCTF flag.

1. Launched the instance and then opened my Webshell. Immediately entered the command to enter the shell ("ssh ctf-player@venus.picoctf.net -p 56974") and was stumped by the password not working. Tried again multiple times until I realized I first need to sign in with my pico credentials before entering the shell command.
2. Once in the system, used "unminimize" to see the hidden files/directories.
3. Used "ls" to see the files. There were two: '1of3.flag.txt' and 'instructions-to-2of3.txt'. Used "cat" with the first file name to see contents, found the first portion of the flag.
4. Used "cat" with second file name, which contained message to navigate to root /
5. Used "ls /" to see what was in root. Found two files of interest: '2of3.flag.txt' and 'instructions-to-3of3.txt'. For some reason I thought I already saw the first file, so I just focused on checking what's in the second file.
6. Tried to "cat instructions-to-3of3.txt" but it wasn't working. Realized I needed to cd into '/' first.
7. Then I used the cat command and I received the second half of the pico flag (it's actually the third portion b/c I skipped over the file with the second portion).
8. Got an error after submitting my answer. Looked through my log and realized I actually have not looked in the '2of3.flag.txt' file and so I used cat to look into it.
9. Found the second portion of the flag there. Put pieces together and successfully submitted answer (picoCTF{xxsh_0ut_0f_\/\/4t3r_3ca613a1}).


### Lets Warm Up | 50 points

Given a hexadecimal, convert it into ASCII. 

1. The question asked what 0x70 would be in ASCII. I pulled up a hexadecimal to ASCII converter, but it took like three different converters before I found one that gave me an actual character.
2. I had to format the answer as a flag, so my answer was picoCTF{p}. This was the converter I used: https://shorturl.at/mwQU3


### Warmed Up | 50 points

Given hex (0x3D), what would the it be in decimal?

1. Used converter and submitted picoCTF{61}. Converter: https://www.atatus.com/tools/hex-to-decimal


### 2Warm | 50 points

Convert given decimal (42) into binary/

1. Used converter and submitted picoCTF{101010}. Converter: https://www.rapidtables.com/convert/number/decimal-to-binary.html


### Based | 200 points

Convert set of different data encodings into text under 45 seconds to receive the flag. 

1. Log into Webshell and run the given command (nc jupiter.challenges.picoctf.org 29221)
2. I basically had to pull up different converters and be able to quickly recognize what type of data encoding I am presented with to put it into the right converter. I timed out the first time because I didn't recognize the octal set of numbers.
3. I tried I second time and was able to do it fast enough. I got binary, octal, and hex encodings. After solving, I was given the flag to submit (picoCTF{learning_about_converting_values_00a975ff}).



## Web Exploitation
### GET aHEAD | 20 points

Look through a given site's server requests info to find the flag. 

1. Looked up what HEAD meant in server request. Used this site: https://developer.mozilla.org/en-US/docs/Web/HTTP/Methods
2. Clicked on given link to site and used inspector to see what's going on. It uses GET and POST methods to change the site color.
3. The hint says I have more than two options, which probably refers to there being the GET and POST methods to either turn the site red or blue. Based off of the challenge's title, I guessed the third option would be HEAD. Looked through the mozilla reference and noticed that these three requests give similar results but in different ways.
4. Looked through Linux notes to see what command to use to check out the website locally. Found curl and decided to use it.
5. Ran "curl <url>:, but it just output the HTML I already looked at manually.
6. Found "curl --help" for shortened manual on curl. Ran it, found '-i' to include protocol response headers.
7. Ran "curl -i <url>" but it didn't work. Just returned the HTML again.
8. Looked up "command to get head info from website" and found "curl -I" here: https://shorturl.at/doAFX
9. Ran "curl -I <url>". Found the answer (picoCTF{r3j3ct_th3_du4l1ty_775f2530}).


### logon | 100 points

Try to log onto a given site and exploit insecurities to find the flag. 

1. Opened the link to the site. It's a login page. Used username 'Joe' and password 'blah'. Gave me message that Joe's password is super secure. Tried logging in with a random username and password, got in but wouldn't show the flag. 
2. Opened inspector. Elements didn't have anything interesting in it, so I looked through the tools and storage had the most interesting info. Saw my two attempted sessions, and I also saw a name 'admin', so I knew that should be important. I didn't quite understand the name and the value stuff going on, but out of the dummy sessions, admin was the only one from the domain jupiter.challenges.picoctf.org.
3. I tried logging in wither username 'admin' and password 'False', but it didn't let me in. I guess that's not how name and value worked.
4. Clicked on admin's value of "False" and decided to change it to "True" to see if it would let me see the flag. Refreshed and it showed the flag (picoCTF{th3_c0nsp1r4cy_l1v3s_d1c24fef}).



## Cryptography
### Mod 26 | 10 points

Convert an ROT13 cypher into text for the flag.

1. Looked up what ROT13 is.
2. Found a ROT13 decoder, entered cipher, submitted the converted text (picoCTF{next_time_I'll_try_2_rounds_of_rot13_wqWOSBKW}).


### Easy1 | 100 points

We're supposed to solve a one time pad, given a table and an encryption key. 

1. Never heard of a one time pad and it shows. I downloaded the table, saw that there were the same amount of characters in the pad and key, and proceeded to use them like x and y coordinates to get my letters. When I submitted, it was wrong and I was devastated because I spent so much time matching the letters up.
2. Thought perhaps there's a decoder for this stuff. Looked up "one time pad decoder" and used the first one. Pasted in my pad and key and was given a more readable answer than what I first came up with (CRYPTOISFUN)
3. Submitted picoCTF{CRYPTOISFUN}



## Reverse Engineering
### Transformation | 20 points

Reverse the content given in file 'enc' to get the flag. 

1. Along with enc, some code that seems to explain the process needed to reverse enc is provided. The hint said to use an online decoder, which I am a fan of.
2. Downloaded enc, copied content. Looked online for a decoder, found CyberChef (https://shorturl.at/aAEMX). Pasted content into input. Output was gibberish.
3. Looked through Cyberchef's settings. Noticed "input character encoding" setting and set it to UTF-8. Still gibberish but more legible. Kept increasing UTF until I got to 16BE and it was legible in the classic picoCTF flag format (picoCTF{16_bits_inst34d_of_8_75d4898b}).


### file-run 1 | 100 points
1. "mkdir file-run1" , "cd file-run1", "wget <url>"
2. Since url is for program 'run', used "chmod +x run" first
3. Hint told me to try using ./ with the file, so I ran "./run" and got the answer (picoCTF{U51N6_Y0Ur_F1r57_F113_47cf2b7b}).



## Forensics
### Matryoshka doll | 30 points

Find files within files until you find the flag.

1. After reading hint, decided I need to use binwalk to solve problem. Used this site for reference: https://linuxcommandlibrary.com/man/binwalk
2. "Mkdir matryoshka", "cd matryoshka", "wget <link>"
3. Basically a cycle of extract files "binwalk -e [file]", check what files are available "ls [file]", go to a directory within the file "cd [file]", ls to see what's there and then repeat.
4. Keep doing that until you get to the flag.txt file. "cat flag.txt" to see the flag (picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32})


### Lookey here | 100 points

Given a big set of text, find the flag. 

1. Opened the file, used Ctrl+F "pico", found the flag (picoCTF{gr3p_15_@w3s0m3_4c479940})



## Binary Exploitation
### Stonks | 20 points

Exploit buddy's API by finding what's wrong in his vuln file. 

1. Running out of time, need to at least start most difficult challenge
2. Looking through vuln file, buddy left comments that point out his program's weakness: no format conditions, and the program prints any input out.
3. Would have to find flag by exploiting this. 


## MOST DIFFICULT
### Investigative Reversing 3 | 400 points

Using a recovered binary and an image, we're supposed to find the flag somewhere.

1. just mentioning I was running out of time.
2. made directory to store my two files. ran "file [filename] to figure out whether they actually are the type they say they are.
3. the image is actually an executable LSB file. used "chmod +x mystery" and "./mystery" but it told me that there is no flag and I need to run the code on a server.
4. That's about as far as I got. 
