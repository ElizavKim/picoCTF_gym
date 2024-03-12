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
1. No hints sadness. Looked through the bash script to understand what it's supposed to do. It seems to take the first file given to it, pick out the text, and print the text into a new text file.
2. Created a new directory called staticaintalwaysnoise and placed the binary fie and the bash file into it.
3. Usually used cat to see contents of file, so I probably need to pass the binary file named 'static' to ltdis.sh. 
