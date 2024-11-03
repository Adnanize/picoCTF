## Challenge 
![image](https://github.com/user-attachments/assets/2c260acf-7fa5-4c72-8205-5c6231693f99)

##Solution

We use "wget" to download the files for the challenge and then we unzip the file using "unzip"

![image](https://github.com/user-attachments/assets/f4cdd1ad-94a4-433b-9c66-b3a092c460f5)

We can see there is a "message.txt" in the "drop-in" folder, and the message contents are the following:

![image](https://github.com/user-attachments/assets/7d05e492-b8a8-41eb-afad-86690a646b6c)

Now, we have to check the commit history of the file, one way to do this is to list all hidden files in the current folder by using "ls -la"

![image](https://github.com/user-attachments/assets/02c3bcee-9a3f-42a7-85b7-889a49ea908a)

There is a hidden folder by the name of ".git", if we go to the folder we can see a file called "COMMIT_EDITMSG", when we "cat" that file we can see the flag.

**Flag**: picoCTF{t1m3m@ch1n3_b476ca06}

![image](https://github.com/user-attachments/assets/f01c9a71-9404-4b6a-8958-9106b808d670)
