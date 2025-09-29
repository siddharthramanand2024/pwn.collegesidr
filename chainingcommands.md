# Module 12: Chaining commands

## Challenge 1
**Chaining with semicolons**

Process:
we can use semicolon to chain commands, here /challenge/pwn and /challenge/college commands
```
hacker@chaining~chaining-with-semicolons:~$ /challenge/pwn; /challenge/college
Yes! You chained /challenge/pwn and /challenge/college! Here is your flag:
pwn.college{Ii7x6lkhjkjrBf9Bava83GVgI7q.QX1UDO0wiMyAzNzEzW}
```
Flag:
>pwn.college{Ii7x6lkhjkjrBf9Bava83GVgI7q.QX1UDO0wiMyAzNzEzW}

## Challenge 2
**Chaining with and &&**

Process:
we can use && to chain commands, here /challenge/first-success and /challenge/second commands.

```
hacker@chaining~building-on-success:~$ /challenge/first-success
hacker@chaining~building-on-success:~$ /challenge/second
Error: /challenge/first-success must be successfully chained with 
/challenge/second using &&
hacker@chaining~building-on-success:~$ /challenge/first-success &&  /challenge/second
Nice chaining! Flag: pwn.college{0_oSjvw4e-G9B_VMQJpEyMAG9LK.0lM0MDOxwiMyAzNzEzW}
```
Flag:
>pwn.college{0_oSjvw4e-G9B_VMQJpEyMAG9LK.0lM0MDOxwiMyAzNzEzW}

## Challenge 3
**Chaining with or ||**

Process:
we can use || to chain commands, here /challenge/first-failure and /challenge/second commands.
```
hacker@chaining~handling-failure:~$ /challenge/first-failure || /challenge/second
Nice chaining! Flag: pwn.college{IZww2TxaAaKNltFLJM2cfoibZip.01M0MDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{IZww2TxaAaKNltFLJM2cfoibZip.01M0MDOxwiMyAzNzEzW}

## Challenge 4
**First shell script**

Process:
we can put all our commands in a file called a shell script and then run it using the shell. we can create file using nano.
```
hacker@chaining~your-first-shell-script:~$ nano x.sh
/challenge/pwn
/challenge/college

hacker@chaining~your-first-shell-script:~$ bash x.sh
Great job, you've written your first shell script! Here is the flag:
pwn.college{gAyCLucLQrRuKJDXiUDy0YhsTzS.QXxcDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{gAyCLucLQrRuKJDXiUDy0YhsTzS.QXxcDO0wiMyAzNzEzW}

## Challenge 5
**Redirecting script output**

Process:
we can also pipe a shell script, which we will be doing in this challenge.
```
hacker@chaining~redirecting-script-output:~$ bash x.sh | /challenge/solve
Correct! Here is your flag:
pwn.college{o1X3bO4mINHrxFfvrb1O0bP0KnU.QX4ETO0wiMyAzNzEzW}
```
Flag:
> pwn.college{o1X3bO4mINHrxFfvrb1O0bP0KnU.QX4ETO0wiMyAzNzEzW}

## Challenge 6
**Executable Shell scripts**

Process:
we can execute a script directly without bash by using chmod to make it executable.
```
hacker@chaining~executable-shell-scripts:~$ nano x.sh
hacker@chaining~executable-shell-scripts:~$ chmod +x x.sh
hacker@chaining~executable-shell-scripts:~$ ./x.sh
Congratulations on your shell script execution! Your flag:
pwn.college{YTbwrhBxtN4iFhhJ_8MMkNAY0xB.QX0cjM1wiMyAzNzEzW}
```
Flag:
> pwn.college{YTbwrhBxtN4iFhhJ_8MMkNAY0xB.QX0cjM1wiMyAzNzEzW}

## Challenge 7
**Executable Shell scripts**

Process:
we can add shebang to specify which intrepereter to run the script.
```
hacker@chaining~understanding-shebangs:~$ nano /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~understanding-shebangs:~$ /challenge/run
Testing your script...
Perfect! Your flag:
Flag: pwn.college{I5InBNC26RU9Z4SMDz9YfsUOVj3.0VOzMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{I5InBNC26RU9Z4SMDz9YfsUOVj3.0VOzMDOxwiMyAzNzEzW}

## Challenge 8
**Scripting with arguments**

Process:
Scripts can accept arguments too.
```
hacker@chaining~scripting-with-arguments:~$ nano /home/hacker/solve.sh

#!/bin/bash
echo "$2 $1"

hacker@chaining~scripting-with-arguments:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-arguments:~$ /challenge/run
Correct! Your script properly reversed the arguments.
Here's your flag:
pwn.college{wICfVdtX7PALSqlxCWVTbdPeM8g.0VNzMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{wICfVdtX7PALSqlxCWVTbdPeM8g.0VNzMDOxwiMyAzNzEzW}

## Challenge 9
**Scripting with if**

Process:
using conditional operator if to write script.
```
hacker@chaining~scripting-with-conditionals:~$ nano /home/hacker/solve.sh

#!/bin/bash
if [ "$1" = "pwn" ]; 
then
  echo college
fi

hacker@chaining~scripting-with-conditionals:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-conditionals:~$ /challenge/run
Correct! Your script properly handles all the conditions.
Here's your flag:
pwn.college{shL8Os-wfC5Pu7QbchWczVptaC1.0lNzMDOxwiMyAzNzEzW}
```
Flag:
>pwn.college{shL8Os-wfC5Pu7QbchWczVptaC1.0lNzMDOxwiMyAzNzEzW}

## Challenge 10
**Scripting with if and else**

Process:
```
hacker@chaining~scripting-with-default-cases:~$ nano /home/hacker/solve.sh

if [ "$1" = "pwn" ]; 
then
  echo college
else
  echo nope
fi

hacker@chaining~scripting-with-default-cases:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-default-cases:~$ /challenge/run
Correct! Your script properly handles the if/else conditions.
Here's your flag:
pwn.college{IloFTcCkp89TNnS7jliAnHBWNyG.01NzMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{IloFTcCkp89TNnS7jliAnHBWNyG.01NzMDOxwiMyAzNzEzW}

## Challenge 11
**Scripting with if and elif**

Process:
```
hacker@chaining~scripting-with-multiple-conditions:~$ nano /home/hacker/solve.sh 

#!/bin/bash

if [ "$1" = "hack" ]; then
  echo "the planet"
elif [ "$1" = "pwn" ]; then
  echo "college"
elif [ "$1" = "learn" ]; then
  echo "linux"
else
  echo "unknown"
fi

hacker@chaining~scripting-with-multiple-conditions:~$ chmod +x /home/hacker/solve.sh
hacker@chaining~scripting-with-multiple-conditions:~$ /challenge/run
Correct! Your script properly handles all the conditions with elif.
Here's your flag:
pwn.college{M6iF6Owl_6IAgQrfubLhqgusGnD.0FOzMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{M6iF6Owl_6IAgQrfubLhqgusGnD.0FOzMDOxwiMyAzNzEzW}

## Challenge 12
**Reading shell scripts**

Process:
we can also read shell scripts.
```
hacker@chaining~reading-shell-scripts:~$ nano /challenge/run
hacker@chaining~reading-shell-scripts:~$ cat /challenge/run
#!/opt/pwn.college/bash

read GUESS
if [ "$GUESS" == "hack the PLANET" ]
then
        echo "CORRECT! Your flag:"
        cat /flag
else
        echo "Read the /challenge/run file to figure out the correct password!"
fi
hacker@chaining~reading-shell-scripts:~$ /challenge/run
hack the PLANET                    
CORRECT! Your flag:
pwn.college{0x3q4q8QCNJqY05N_WEutka-OOY.0lMwgDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{0x3q4q8QCNJqY05N_WEutka-OOY.0lMwgDOxwiMyAzNzEzW}
