First we have to use "wget" tool to download the relevant files from the picoCTF website as it shown.

![image](https://github.com/user-attachments/assets/f8e5e2e8-7b9e-412f-8957-7c569123b342)

The resulted file after downloading is zipped, therefore, we have to unzip the file by using "unzip" and we have the resulted directory "home"

![image](https://github.com/user-attachments/assets/0be11746-3e4b-4ddb-842a-7414f12eeb22)


After accessing it the path, we have the following game file "guessing_game.sh", to launch this we use "bash guessing_game.sh"

![image](https://github.com/user-attachments/assets/3adf0167-19bf-4489-b2d3-27dadc6063c3)


As you can see, we are prompted to pick a number between 1 to 1000 and you are suppose to guess the number.

**Catch**: You only have 10 guess!!!

Binary search is an efficient algorithm for finding a target value within a sorted range by repeatedly dividing the range in half. Here’s how it works in the context of guessing a number between 1 and 1000 within 10 tries:

* Start by guessing the middle number between 1 and 1000 (which is 500).
* Get feedback: If the number is higher, focus on the upper half (501–1000). If it's lower, focus on the lower half (1–499).
* Pick the middle of your new range based on the feedback and guess again.
* Repeat this process: each time, cut your range in half by guessing the middle of the remaining numbers.
* Continue narrowing down until you find the exact number or reach 10 tries.

**By halving each time, you'll find the number in 10 guesses or fewer!**
