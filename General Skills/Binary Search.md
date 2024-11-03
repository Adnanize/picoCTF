## Challenge 

![image](https://github.com/user-attachments/assets/5749e454-2af2-4f91-b608-94bc435cbf43)


## Solution 

First we have to use "wget" tool to download the relevant files from the picoCTF website as it shown.

![image](https://github.com/user-attachments/assets/f8e5e2e8-7b9e-412f-8957-7c569123b342)

The resulted file after downloading is zipped, therefore, we have to unzip the file by using "unzip" and we have the resulted directory "home"

![image](https://github.com/user-attachments/assets/0be11746-3e4b-4ddb-842a-7414f12eeb22)


After accessing it the path, we have the following game file "guessing_game.sh", to launch this we use "bash guessing_game.sh"

![image](https://github.com/user-attachments/assets/3adf0167-19bf-4489-b2d3-27dadc6063c3)


As you can see, we are prompted to pick a number between 1 to 1000 and you are suppose to guess the number.

**Catch**: You only have 10 guess!!!

![image](https://github.com/user-attachments/assets/2d2901c7-b5b5-4d25-8166-2fe5a1ef60a5)

Yes I know for some reason the flag isn't showing but the soultion is correct lmao😂😂😂

## Explanation 
Binary search is an efficient algorithm for finding a target value within a sorted range by repeatedly dividing the range in half. Here’s how it works in the context of guessing a number between 1 and 1000 within 10 tries:

* Start by guessing the middle number between 1 and 1000 (which is 500).
* Get feedback: If the number is higher, focus on the upper half (501–1000). If it's lower, focus on the lower half (1–499).
* Pick the middle of your new range based on the feedback and guess again.
* Repeat this process: each time, cut your range in half by guessing the middle of the remaining numbers.
* Continue narrowing down until you find the exact number or reach 10 tries.

**By halving each time, you'll find the number in 10 guesses or fewer!**

So, in our instance, we had the following:

* Start with 500 (middle of 1 and 1000) → Too high.
* Guess 250 (middle of 1 and 499) → Too high.
* Guess 125 (middle of 1 and 249) → Too low.
* Guess 188 (middle of 126 and 249) → Too low.
* Guess 219 (middle of 189 and 249) → Too high.
* Guess 203 (middle of 189 and 218) → Too low.
* Guess 211 (middle of 204 and 218) → Too low.
* Guess 215 (middle of 212 and 218) → Too high.
* Guess 213 (middle of 212 and 214) → Correct!

***Each guess cuts the range in half, quickly leading to the correct number, 213!***

