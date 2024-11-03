## Challenge 

Make sure to have the instance running to get the extra guidance.

![image](https://github.com/user-attachments/assets/325b39b2-58bf-41b3-a884-86f2be064f93)


## Soultion 

Pretty straight forward, we use the "ssh" tool to login remotely as ctf-player to titan.picoctf.net at port 53005.
We do this by using the command "ssh ctf-player@titan.picoctf.net -p 53005". Afterwards, it will prompt to accept a fingerprint where you will say "yes". The password is given from the Challenge when you launch the instance. 

**Flag**: picoCTF{s3cur3_c0nn3ct10n_5d09a462}

![image](https://github.com/user-attachments/assets/d76278c1-7ba7-4eaf-9453-04f822060c9e)

## Explanation

**Command**:  ssh ctf-player@titan.picoctf.net -p 53005 
* ssh: Starts an SSH session.
* ctf-player@titan.picoctf.net: Specifies the username (ctf-player) and the server address (titan.picoctf.net).
* -p 57179: Indicates the port number (57179), which is non-standard and must be specified. Your port number will be different obviously 
* After entering this command, you'll be prompted for the password if one is required. Once connected, you’ll have access to the server with the ctf-player account on port 57179. 
