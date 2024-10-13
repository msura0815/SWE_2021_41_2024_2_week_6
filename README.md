# SWE_2021_41_2024_2_week_6

## Week 4 Assignment
* My Repository (Week 4)
  >https://github.com/msura0815/SWE_2021_41_2024_2_week_4
* Description
* The goal of the week 4 assignment is write an algorithm to find 'Happy Number'. 

   The given constraints are as follows:
  * Starting with any positive integer, replace the number by the sum of the squares of its digits. 
  * Repeat the process until the number equals 1 (where it will stay), or it loops endlessly in a cycle which does not include 1. 
  * Those numbers for which this process ends in 1 are happy. 
  * Return true if n is a happy number, and false if not.
  * Range : 1 <= n <= $2^{31}$ - 1

```python
def isHappy(n): # main function
    def cal(n):
        sum = 0
        strn = str(n)  # to calculate the length of digits
        tens = len(str(n)) # length of digits
        for i in range(tens): # iterate for the number of digits
            sum += int(strn[i]) ** 2
        return sum

    temp = []  # save the temporarary values
    while n != 1 and n not in temp: # until the number equals 1
        temp.append(n)
        n = cal(n)
    return n == 1  # True / False
```

1. To satisfy the given conditions, it was necessary to break down the input number into its individual digits and square them. \
Therefore, this function converts the integer input to a string and uses indexing to access each digit separately and operate them. \
2. Additionally, this calculation must be repeated until it can be determined whether it ultimately reaches 1. \
So this operation is structured to store the results in temp, allowing for later output.

```python
num = int(input("Please enter a positive integer: ")) # for user

if num < 1 or num > 2**31 - 1: #constraints
    print("input error")
else:
    print(isHappy(num))  # function
```

1. According to the given conditions, an integer within a specified range must be input by the user. So I included a prompt to enter a positive integer.
2. However, Since the default input is in string format, it has been converted to an integer.
3. Because only numbers within the specified range (1 <= n <= $2^{31}$ - 1) can be inputs for this function, exception handling was implemented.



## Week 5 Assignment
> ```python
> docker exec ossp-container cat /etc/os-release
>  ```
> This is the command line to check the operating system information in my container(ossp-conatiner).\
> The output is as follows: 
![image](https://github.com/user-attachments/assets/9e4b78b3-cb67-4920-beb9-3b13102dc1e3)
> It can be observed that the ossp-container is using Ubuntu version 24.04.1 LTS.

> ```python
> docker exec ossp-container git --version
> docker exec ossp-container python3 --version
>  ```
> These are the command lines to check the version of GitHub and Python3 installed in my container (ossp-container).\
> The outputs are as follows:
> ![image](https://github.com/user-attachments/assets/f46a262c-1ae6-451c-8d45-9c6b42f883c8)
> It can be observed that the ossp-container is using git version 2.43.0 and python3 3.12.3.

>```python
>docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
>```
> This is the command line to check where the container is mounted. \
> The output is as follows:
> ![image](https://github.com/user-attachments/assets/a27ecd9a-b357-440a-a3a1-055a57e798c0)
> It can be observed the mounted directories.














