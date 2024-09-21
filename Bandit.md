## Bandit - Saswath A

As of in the website of bandit game, they said to connect to their Ip server through ssh(Secure Shell). So I searched some about ssh in google to know about it and how it works. After knowing somethings, I tried to enter the bandit server with the user given and entered successfully.

Level 0:                                                                        

    So after entering the level 0,I read the readme text file through cat command and got the password for the first level. And then exit from the server and logged to the server from another server (i.e) bandit1. Entered the server successfully.

    Password:ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

Level 1:

    For entering in the level 2, I need a password from a file in level 1 which is named as ‘-’. As the name is ‘-’,it cannot be open as dash is considered as argument or command. So I googled and found out how to open the dashed file using command (./). It deactivate the argument and show as normal text.

    Password:263JGJPfgU6LtdEvgfWU1XP5yac29mFx

Level 2:

    In level 2, the password is contained in a space named file which means the terminal gets them as separate command or text. So to avoid this and open it, we can use “” to tell the terminal that is a text. This method I saw internet but I actually used to open the file by just entering tab after cat command which showed “cat spaces/ in/ this/ filename/” and got the password through which I logined into level 3.

    Password:MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

Level 3:

    In level 3, the password file was in inhere directory. So I changed to inhere directory but as it is the hidden file it can’t be seen by just ls command. And I googled how to open hidden file and came to know that to use ls -a. So after finding the name of hidden file.I used cat to know the password and entered level 4.

    Password:2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

Level 4:

    In the inhere directory, there are couple of files. So in the website, it is mentioned that the file is human-readable file. Through internet, I came to know that only two file type is human-readable. They are ASCII and Unicode. So after that I used file command to know the type of file and sort it out. And I got a single file which is ASCII text file. And I got the password by reading the file.

    Password:4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

Level 5:

    Same as level 5, there some specification for the password containing file like  human-readable, file size is 1033 bytes and non-executable. So To find the size of file, I used du -a -b | grep 1033 , this I saw in internet because I got stuck with it.  And I found and directory and file. So I used viewed the file and got the password.

    Password:HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

Level 6:

    As the filename is not mentioned in the website but the criteria are given, we need to find the file by that. So here the fnd command helped me to find the specfic file.
    I used several flag like -type, -user, -group, size. And I got the location of file and used it to view the text file and got the password.

    Password:morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

Level 7:

    Here the password is located next to a word millionth in a file data.txt. This can be done just by using grep which help us to find the word in the text. AS the password is in the same line the password is also is printed.

    Password:dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

Level 8:

    So here the password is stored in a file where many lines are repeated but the password alone not repeated. Hence I need to sort a specific thing, I need to use uniq command which selects the unique one from txt. Thus after that I got the password.

    Password:4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

Level 9:

    In this level, they have given txt and password is in one of the few human-readable strings, preceded by several ‘=’ characters. As the strings command finds human-readable strings in files. I used strings and grep to find the password and got it successfully.

    Password:FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

Level 10:

    As the file data.txt contains base64 encoded data, it needs to be decoded to view the password. And linux has a comand called base64 -d to decode which I used to decode the file and know the password.

    Password:dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr


Level 11:

    Here the password is in the data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions.
    To view the password, there is a command called tr which allows replacing characters with others. So I replaced the old characters with new characters. And I got the password.

    Password:7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

Level 12:

    In this level the file is a hexdump of a file that has been repeatedly compressed. So to work the file, I created a new directory in /tmp and copied the file to there. So the main objective is to find the password, thus we revert the hexdump and get the actual data. Actually this was very confusing and had spent lot of time to get what to do. So  the file is compressed many layer. After reverting I checked the file and found that is gzip compressed, so I decompressed by renaming and decompressed. Also then it was encoded by bzip . So the same process of decompressing went. And then again it was gziped and I decompressed the same way. Now we have an archive which can be extracted by using tar. Again its was bzips2 and then tar archive and then atlast gzip compressed file. This was decompressed successfully and got the password.

    Password:FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn


Level 13:

    In this level the password is in key type, so I used scp to connect to the remote machine and get the key which stored in my own directory. And I got denied to log in because it was too open to everyone which I changed through chmod 700 command. And logined to the next level through the key.

    Password:MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

Level 14:

    After getting the password from the location mentioned in the previous level instruction, we need to connect to a specific port for getting the current level password. I used telnet(command) to access network service and get the password by previous password. There are also other ways to open it like netcat, etc.

    Password:8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

Level 15:

    To get the password of level 16, we need to submit the password of current level(15)to port 30001 on localhost using SSL/TLS encryption. So openssl s_client is the command that connects the port(server) using SSL/TLS. Thus I used them and submited the password and got the required password.

    Password:kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

Level 16:

    To login this server, I need the password from one of the port ip in the range of 31000-32000. So by reading about it in google, I understood that we should use port scanner to identify the version i.e which listens to our txt and give us the credentials. So I used nmap which is network scanner. The command I used is nmap -sV localhost -p 31000-32000. After this I avoid the echo service type because they just send back what we send. So I choose the port:31790 which had unknown service to connect with that port and get the password.
    But I encountered a problem when I entered the level 16 password, it showed keyupdate because the starting letter of password is k. So It assume that the client(me) request for a keyupdate. Thus I have to find a alternate way for that. After multiple search, I found out the way through the man page of openssl-s_client. That I should quiet the argument for k. So I used the command “openssl s_client -connect localhost:31790 -quiet” to connect the server. Then it successfully worked and then same as level 14 I used key to get in the level 17.

    Password:EReVavePLFHtFlFsjn3hyzMlvSuSAcRD

Level 17: 

    For level 18, the password is in password.new. But the condition is that the only line that has been changed between passwords.old and passwords.new contains the password. So I used diff command which showed the changed line in both one. By this I got the password.

    Password:x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

Level 18:

    In level 18, when I try to log in the server it just kicked me off with a great sendoff message Bye Bye!!. This was because they have modified the .bash.rc . So I have find other way where I should command to view the password from readme before the .bash.rc execute. Thus you can write “ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme”

    Password:cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

Level 19:

    So to get password of level 20, we need to view the bandit20 file in /etc/bandit_pass. But the permission for the file is not given to user bandit19 but it is given to bandit20. I know it by using ls -l command. Then after googling it I came to know that ./bandit20 can run the command as another user.

    Password:0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

Level 20:

    For this level password, we want to give the previous level password to 1234 port using echo command and netcat. The command I used  “echo -n ‘0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO’ | nc -l -p 1234”. In nc -l argument is used to listen the port. Then I used the suconnect and the port ‘1234’ to listen and give the password.

    Password:EeoULMCra2q0dSkYj561DX7s1CpBuOBt

Level 21:

    As per the webisite of bandit, they have mentioned that cron is program running automatically at regular interval. So when i cd to /etc/cron.d/ , I found out multiple file but i choose "cronjob_bandit22" because i was searchign for the password of level 22. Thus after viewing that using cat command, it executes bash script every min of every hour. After that I used cat again to view the cron syntax  and it started to assign the password into a file in tmp. Then I used cat to view the password

    Password:tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
    
Level 22:
    PASSWORD : 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga


 
 








