# Module 6: Practicing Piping

## Challenge 1
**Redirecting output**

Process:
using > to redirect output from PWN to College.

```
hacker@piping~redirecting-output:~$ echo PWN>COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag: pwn.college{AXH1ofFCGbPansf6k_VWVmxvGes.QX0YTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{AXH1ofFCGbPansf6k_VWVmxvGes.QX0YTN0wiMyAzNzEzW}

## Challenge 2
**Redirecting output**


Process:
using > to redirect output from PWN to College without using echo.

```
hacker@piping~redirecting-more-output:~$ /challenge/run > myflag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
hacker@piping~redirecting-more-output:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{cD3bUQ00OXkFt3L_5H6qoKtU7K9.QX1YTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{cD3bUQ00OXkFt3L_5H6qoKtU7K9.QX1YTN0wiMyAzNzEzW}

## Challenge 3
**Appending output**

Process:
using >> to append output.

```
hacker@piping~appending-output:~$ /challenge/run >>  /home/hacker/the-flag
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!

hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{8TOhjxajDJPs1qTJkJZ3SSkIZ0W.QX3ATO0wiMyAzNzEzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```
Flag:
> pwn.college{8TOhjxajDJPs1qTJkJZ3SSkIZ0W.QX3ATO0wiMyAzNzEzW}

## Challenge 4
**Redirecting errors**

Process:
using 2> to redirect errors.
acc to problem redirect output to myflag and errors to instructions.

```
hacker@piping~redirecting-errors:~$ /challenge/run > myflag 2> instructions
hacker@piping~redirecting-errors:~$ cat myflag

[FLAG] Here is your flag:
[FLAG] pwn.college{IBTAxdhZAfrhqg1EZ6n891HN7Um.QX3YTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{IBTAxdhZAfrhqg1EZ6n891HN7Um.QX3YTN0wiMyAzNzEzW}

## Challenge 5
**Redirecting input**

Process:

first we use echo and > to store college in pwn.
then we redirect it as input using < to /challenge/run.
```
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run <PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{M370Znhodjz-gZsdBa_igb0u3BF.QXwcTN0wiMyAzNzEzW}
```
Flag:
> pwn.college{M370Znhodjz-gZsdBa_igb0u3BF.QXwcTN0wiMyAzNzEzW}

## Challenge 6
**Grepping stored results**

Process:
first we append output using >>.
then we grep through the resulting file with the string "pwncollege"to find the flag.

```
/challenge/run > /tmp/data.txt
hacker@piping~grepping-stored-results:~$ grep "pwn.college" /tmp/data.txt
pwn.college{I8jojJ-IeJVH24KbMgE3JAP9VvB.QX4EDO0wiMyAzNzEzW}
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp/data.txt
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.

hacker@piping~grepping-stored-results:~$ grep "pwn.college" /tmp/data.txt
pwn.college{I8jojJ-IeJVH24KbMgE3JAP9VvB.QX4EDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{I8jojJ-IeJVH24KbMgE3JAP9VvB.QX4EDO0wiMyAzNzEzW}

## Challenge 7
**Grepping live output**

Process:
instead of > we can use |(pipe) command to pass commands directly without creating a new file.
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep "pwn.college"
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{AMurqMGsbRgms8pOK9AByTxvk2s.QX5EDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{AMurqMGsbRgms8pOK9AByTxvk2s.QX5EDO0wiMyAzNzEzW}

## Challenge 8
**Grepping errors**

Process:
we cant pipe standard error directly so we use >& to do the job.
```
hacker@piping~grepping-errors:~$ /challenge/run 2>&1 | grep "pwn.college"
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/8b4vn1iyn6kqiisjvlmv67d1c0p3j6wj-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{UwNcuENipZ1HghuyPUnGB6OLANg.QX1ATO0wiMyAzNzEzW}
```
Flag:
> pwn.college{UwNcuENipZ1HghuyPUnGB6OLANg.QX1ATO0wiMyAzNzEzW}

## Challenge 9
**Filtering with grep -v**

Process:
use grep -v to find the non-matching pattern.
```
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v "DECOY"
pwn.college{QKlO8Rigw5UHsBbCZmmNdGVYMaU.0FOxEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{QKlO8Rigw5UHsBbCZmmNdGVYMaU.0FOxEzNxwiMyAzNzEzW}

## Challenge 10
**Duplication with tee**

Process:

first we use tee to duplicate output in a pwnoutput file.

then we read the contents of the file to get the secret code.

after that we pipe the input to output along with the secret code to get the flag.
```
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn | tee pwn_output
Processing...
cYou are trying to use 'tee' *instead* of /challenge/college. Use it *between* 
/challenge/pwn and /challenge/college!
You must pipe the output of /challenge/pwn into /challenge/college (or 'tee' 
for debugging).
hacker@piping~duplicating-piped-data-with-tee:~$ cat pwn_output
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "krwwRlkI"
hacker@piping~duplicating-piped-data-with-tee:~$ /challenge/pwn --secret krwwRlkI | /challenge/college
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{krwwRlkI6_8Zg6qayFr8H9Y_qcR.QXxITO0wiMyAzNzEzW}
```
Flag:
> pwn.college{krwwRlkI6_8Zg6qayFr8H9Y_qcR.QXxITO0wiMyAzNzEzW}


## Challenge 11
**process substitution**

Process:
Use process substitution with diff to compare the outputs of these two programs and find your flag.
```
hacker@piping~process-substitution-for-input:~$ diff <(/challenge/print_decoys) <(/challenge/print_decoys_and_flag)
79a80
 pwn.college{wLtlVVALLd6AKGs7qSEvdxbDAwA.0lNwMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{wLtlVVALLd6AKGs7qSEvdxbDAwA.0lNwMDOxwiMyAzNzEzW}


## Challenge 12
**writing multiple programs**

Process:

tee duplicates the output of /challenge/hack.

( /challenge/the )  sends one copy to /challenge/the.

( /challenge/planet )  sends another copy to /challenge/planet.

 /dev/null discards the original stdout to avoid printing it twice.
```
hacker@piping~writing-to-multiple-programs:~$ /challenge/hack | tee >( /challenge/the ) >( /challenge/planet ) > /dev/null
Congratulations, you have duplicated data into the input of two programs! Here 
is your flag:
pwn.college{cHLXbNwxqYVQeHRXf3vlAp-RRhg.QXwgDN1wiMyAzNzEzW}
```
Flag:
> pwn.college{cHLXbNwxqYVQeHRXf3vlAp-RRhg.QXwgDN1wiMyAzNzEzW}

## Challenge 13
**split piping stderr and stdout**

Process:

The point is to handle stdout and stderr from the /challenge/hack program separately in a single command.

Using a normal pipe (|) to send the standard output of /challenge/hack to the standard input of /challenge/planet.

```
hacker@piping~split-piping-stderr-and-stdout:~$ /challenge/hack 2> >(/challenge/the) | /challenge/planet
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{g0Uv9RlDh6q1GYgrDqweaJflEJ2.QXxQDM2wiMyAzNzEzW}
```
Flag:
> pwn.college{g0Uv9RlDh6q1GYgrDqweaJflEJ2.QXxQDM2wiMyAzNzEzW}

## Challenge 14
**split piping stderr and stdout**

Process:

First we create the FIFO using the mkfifo command.

Next we write to the FIFO.

Read the Flag from the FIFO

```
hacker@piping~named-pipes:~$ mkfifo /tmp/flag_fifo
hacker@piping~named-pipes:~$ /challenge/run > /tmp/flag_fifo &
You're successfully redirecting /challenge/run to a FIFO at /tmp/flag_fifo! 
Bash will now try to open the FIFO for writing, to pass it as the stdout of 
/challenge/run. Recall that operations on FIFOs will *block* until both the 
read side and the write side is open, so /challenge/run will not actually be 
launched until you start reading from the FIFO!
[1] 155
hacker@piping~named-pipes:~$ cat /tmp/flag_fifo
You've correctly redirected /challenge/run's stdout to a FIFO at 
/tmp/flag_fifo! Here is your flag:
pwn.college{sw586GO0yni9inCWcgeghTB2KWK.01MzMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{sw586GO0yni9inCWcgeghTB2KWK.01MzMDOxwiMyAzNzEzW}


