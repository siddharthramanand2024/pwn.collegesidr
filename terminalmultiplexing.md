# Module 13: Terminal Multiplexing

## Challenge 1
**Launching screen **

Process:
we can use $screen to create virtual terminals.
```
Congratulations! You're inside a screen session!
Here's your flag:
pwn.college{AyxjCT2ySDj_M0-5yxCkEnEH-Tm.0VN4IDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{AyxjCT2ySDj_M0-5yxCkEnEH-Tm.0VN4IDOxwiMyAzNzEzW}

## Challenge 2
**Detaching and Attaching **

Process:
we can detach from a screen using ^+A followed by d.
for reattaching we use screen -r.
```
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen

[detached from 147.pts-0.terminal-multiplexing~detaching-and-attaching]

hacker@terminal-multiplexing~detaching-and-attaching:~$ /challenge/run
Found detached screen session: 147.pts-0.terminal-multiplexing~detaching-and-attaching
Sending flag to your screen session...

Flag sent! Now reattach to your screen session with:
screen -r

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching:~$ screen -r
hacker@terminal-multiplexing~detaching-and-attaching:~$ echo Yes! Flag is: pwn.college{s8UuiiKcppaeYRrRpAVBbTT5qtf.0lN4IDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{s8UuiiKcppaeYRrRpAVBbTT5qtf.0lN4IDOxwiMyAzNzEzW}

## Challenge 3
**Finding sessions **

Process:
we can use ls to list the screens.
```
hacker@terminal-multiplexing~finding-sessions:~$ screen -ls
There are screens on:
        158.pts-0.terminal-multiplexing~launching-screen        (Remote or dead)
        147.pts-0.terminal-multiplexing~detaching-and-attaching (Remote or dead)
        144.session_c3835918ea9ee858    (Detached)
        147.session_3d655efb1e0f1fd9    (Detached)
        150.session_6dfab3ce17df247d    (Detached)
5 Sockets in /home/hacker/.screen.

hacker@terminal-multiplexing~finding-sessions:~$ screen -r 150
congratulations! You found the right session!
hacker@terminal-multiplexing~finding-sessions:~$  echo pwn.college{0q_gfGX8KnWZopZ2q1tRaD-cCLM.01N4IDOxwiMyAzNzEzW}
pwn.college{0q_gfGX8KnWZopZ2q1tRaD-cCLM.01N4IDOxwiMyAzNzEzW}
```
Flag:
>pwn.college{0q_gfGX8KnWZopZ2q1tRaD-cCLM.01N4IDOxwiMyAzNzEzW}

## Challenge 4
**Switching windows **

Process:
we can do operations on windows using multiple key shortcuts.
```
hacker@terminal-multiplexing~switching-windows:~$  cat <<MSG
 Excellent work! You found window 0!
Here is your flag: pwn.college{AVK1oewn-DOi7QvHkf5W1Uix0Ml.0FO4IDOxwiMyAzNzEzW}
```
Flag:
>pwn.college{AVK1oewn-DOi7QvHkf5W1Uix0Ml.0FO4IDOxwiMyAzNzEzW}


## Challenge 5
**detaching and attaching (tmux) **

Process:
do same using screen younger version tmux.
```
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux
[detached (from session 0)]
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ /challenge/run
Found detached tmux session: 0
Sending flag to your tmux session...

Flag sent! Now reattach to your tmux session with:
tmux attach

You'll find the flag waiting for you there!
hacker@terminal-multiplexing~detaching-and-attaching-tmux:~$ tmux a
Congratulations, here is your flag: pwn.college{0CSZmguu9E4ivWtYv4aP7QAO7u7.0VO4IDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{0CSZmguu9E4ivWtYv4aP7QAO7u7.0VO4IDOxwiMyAzNzEzW}

## Challenge 6
**Switching windows in tmux **

Process:
```
 Excellent work! You found window 0!
> Here is your flag: pwn.college{QFFjhPtud5lrmQE82g-NiVXjKbm.0FM5IDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{QFFjhPtud5lrmQE82g-NiVXjKbm.0FM5IDOxwiMyAzNzEzW}
