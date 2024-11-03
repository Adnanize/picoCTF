## Challenge 

![image](https://github.com/user-attachments/assets/ff1a3098-110d-4253-931c-6929d5503eab)


## Solution 

First of all download the files by using "wget" and unzip them by using "unzip"

![image](https://github.com/user-attachments/assets/f76d1418-1acf-4f0b-9c69-a175a287fdc7)

You'll see that there is a file called "flag.py"

![image](https://github.com/user-attachments/assets/da4371b0-ddf0-4c20-af05-9093b7fb1736)

By using "git branch -a" to list all branches in your Git repository, including both local and remote branches.

![image](https://github.com/user-attachments/assets/f32574a0-1624-40f4-b4a2-eba6e2c4d6e7)

We can see the following branches

**NOTICE**: the branch with an  asterisk * next before it indicates which branch are you currently in.

![image](https://github.com/user-attachments/assets/cfc7551f-c700-4f5e-953a-e8373bb692dd)



Now, we’re simply switching between branches to check the progress of each one on the "flag.py" file.

We do this by using:

1 - "git checkout feature/part-1"

2 - "git checkout feature/part-2"

3 - "git checkout feature/part-3"

We can see how each branch prints a part of the flag.

![image](https://github.com/user-attachments/assets/c6734c3c-e13b-477f-8a0d-9b3c520cff5c)

Now we merge the files to the main branch.

feature/part-1

![image](https://github.com/user-attachments/assets/140fa80d-3272-44dc-9b7f-3c4a00485e81)

feature/part-2

![image](https://github.com/user-attachments/assets/1f5def02-758f-4699-9f06-082e519f1846)

feature/part-3

![image](https://github.com/user-attachments/assets/a71d4e3d-89da-4f1a-b0b9-a9b919382b05)


There was a slight problem that resulted in the python code which was extra unrelated syntax. We can just erase them in a text editor and run the code again.

![image](https://github.com/user-attachments/assets/3a1710fb-069f-41e1-bff6-a64cc6ef4fbd)


Now we have the final flag.

**Flag**: picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}

![image](https://github.com/user-attachments/assets/427907f4-1025-44bc-8c37-8bd3a7c4bfbc)


## Explanation

Each branch—feature/part-1, feature/part-2, and feature/part-3—contained different sections of work or "progress" toward constructing the full flag in flag.py. Each branch likely represented a separate part of the flag or a segment of code essential for revealing the full flag content.

By merging these branches into main, we effectively combined the individual pieces. This final merge integrated all the incremental progress from each branch, resulting in a complete, cohesive flag.py file on the main branch. This approach is common in collaborative projects where different branches hold different parts of a solution, and merging them unifies these contributions into a final, functional form.
