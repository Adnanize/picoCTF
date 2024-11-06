## Challenge

![image](https://github.com/user-attachments/assets/34279472-efe4-4863-89c6-041a0478c65e)


## Solution 

First we would like to netcat to the leaking server to see what it will show us.

By using ``` nc tethys.picoctf.net 56801 ```

We can see a password displaying,** My_Passw@rd_@1234**

![image](https://github.com/user-attachments/assets/d5d48334-84e9-4ff8-b102-f8940fda27e2)

Now we will netcat to the other given server by using ``` nc tethys.picoctf.net 63976 ```

We can see that it prompts us to enter a password, we will enter the extracted password ** My_Passw@rd_@1234**

![image](https://github.com/user-attachments/assets/c4b56526-cde1-4a67-aab1-ffb7816ac622)

Now we prompted with another 2 generic questions, we can answe them by the following.

**What is the top cyber security conference in the world?**

DEF CON

**The first hacker ever was known for phreaking(making free phone calls), who was it?**

John Draper 

Now we are inside the player channel.

![image](https://github.com/user-attachments/assets/fe5a4822-0b2d-42f6-a1ba-44fd8cb46b2a)

If we do a simple ```ls``` we can see two files

1 - banner

2 - text

Both seems to be useless information as of now, but keep an eye of the banner file as we will use it in a moment.

![image](https://github.com/user-attachments/assets/243f8be3-da97-415b-962e-6e24d3a98b65)

Since we did not get anywhere we wil need to dig deeper, we can try to list files/directories in the root folder because some files can be hidden in that directory that requiries root privileges.

We can see two files
1 - flag.txt
2 - script.py

![image](https://github.com/user-attachments/assets/74322973-7dca-46a8-94c9-ee449a44b895)
 
You might think ohh we found the flag right??, No, unfortunately because the file needs root privileges and we do not have that.

![image](https://github.com/user-attachments/assets/8f7e5c82-01ca-40ac-8468-89013cfe44d0)

Now lets view the **script.py** file, and we see something intresting. At the begining of the code we can see a try except part.
Where it tries to open the banner file from the home directory of "player" and if it fails it will print a banner manually.

![image](https://github.com/user-attachments/assets/946d2cac-260e-4c4c-aea5-793118544793)

Now we will go back to the home directory and delete the already existing banner file and use a **symlink**.
Where we will make banner point to the flag.txt file. In other words the script.py file will run and open the banner file, due to symlink, the banner file will be pointing to the flag.txt where the flag is,
Hence, when we run the code the flag should be printed right?  

``` ln -s /root/flag.txt banner ```

creates a symbolic (soft) link named banner that points to /root/flag.txt. Here’s a breakdown of each part:

```ln```: This is the command used to create links in Linux.

```-s```: The -s flag specifies that the link should be symbolic (also called a "soft link"). Unlike a hard link, a symbolic link is more like a shortcut that points to another file's path.

```/root/flag.txt```: This is the target file you want to link to.

```banner```: This is the name of the symbolic link that will point to /root/flag.txt.

After running this command, accessing banner will display the contents of /root/flag.txt (if you have the necessary permissions to view it

![image](https://github.com/user-attachments/assets/8f975b4b-887c-4aa9-8d0d-108eb89c908e)

However when we run the code now the flag still does not show, very strange right?
This happens because the user "player" does not have root privileges and to view the "flag.txt" we had to get root privileges. Therefore, when running the code, the flag did not display.
 
![image](https://github.com/user-attachments/assets/e1ec6446-3fea-4caa-8243-beb7a888421b)

The question is how do we get to root to view the flag, somthing we can experiment with is to netcat to the server again, there could be a chance that it was already running as root while connecting.
And there you go, we can see that flag right there.

**Port number is different here because I had to restart the instance.**

![image](https://github.com/user-attachments/assets/439ec0c7-6735-402a-ab45-7bbfd4a49b20)


