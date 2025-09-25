# Module 9: Processes and Jobs

##  Challenge 1 
 **Listing processes using ps**

Process:
use ps command to find running flag.
```
hacker@processes~listing-processes:~$ ps aux | grep /challenge
root         132  0.0  0.0   4132  2560 ?        S    15:26   0:00 /challenge/14864-run-11658
hacker       161  0.0  0.0 230696  2560 pts/0    S+   15:31   0:00 grep --color=auto /challenge
hacker@processes~listing-processes:~$ /challenge/14864-run-11658
Yahaha, you found me! Here is your flag:
pwn.college{sPbrMlc6J7gJAbESMK_K9Xx5rTb.QX4MDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{sPbrMlc6J7gJAbESMK_K9Xx5rTb.QX4MDO0wiMyAzNzEzW}

## Challenge 2
**killing processes**

Process:
use ps to list processes to find the process to kill.
then use kill command with pid.
```
hacker@processes~killing-processes:~$ ps aux | grep dont_run
hacker       136  0.0  0.0 231576  3520 ?        Ss   15:49   0:00 /challenge/dont_run
hacker       163  0.0  0.0 230696  2560 pts/0    S+   15:51   0:00 grep --color=auto dont_run
hacker@processes~killing-processes:~$ kill <136>
bash: syntax error near unexpected token `136'
hacker@processes~killing-processes:~$ kill 136
hacker@processes~killing-processes:~$ /challenge/run
Great job! Here is your payment:
pwn.college{4TDL83Dotmn4p8zwybOHl4qlBMS.QXyQDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{4TDL83Dotmn4p8zwybOHl4qlBMS.QXyQDO0wiMyAzNzEzW}

## Challenge 3
**Interrupting process**

Process:
use ^C to interrupt process.
```
hacker@processes~interrupting-processes:~$ /challenge/run
I could give you the flag... but I won't, until this process exits. Remember, 
you can force me to exit with Ctrl-C. Try it now!
^C
Good job! You have used Ctrl-C to interrupt this process! Here is your flag:
pwn.college{I_71y7Ghhk8p39NpGtuMHQCJgVB.QXzQDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{I_71y7Ghhk8p39NpGtuMHQCJgVB.QXzQDO0wiMyAzNzEzW}

## Challenge 4
**Misbehaving process**

Process:
again use ps to list decoy command and then use kill command with its pid.
```
hacker@processes~killing-misbehaving-processes:~$ ps aux | grep /challenge/decoy
root         139  0.0  0.0   5204  3520 ?        S    15:58   0:00 su -c exec /challenge/decoy > /tmp/flag_fifo hacker
hacker       142  0.0  0.0  13516  9280 ?        Ss   15:58   0:00 /usr/bin/python /challenge/decoy
hacker       168  0.0  0.0 230696  2560 pts/0    S+   16:00   0:00 grep --color=auto /challenge/decoy
hacker@processes~killing-misbehaving-processes:~$ kill 142

/challenge/run
Sending the flag to /tmp/flag_fifo!
pwn.college{EJQIELY34s46kdCUEbRWkGFYupA.0FNzMDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{EJQIELY34s46kdCUEbRWkGFYupA.0FNzMDOxwiMyAzNzEzW}


## Challenge 5
**Suspending process**

Process:
use ^z to suspend process.
```
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         146     136  0 16:12 pts/0    00:00:00 bash /challenge/run
root         148     146  0 16:12 pts/0    00:00:00 ps -f

I don't see a second me!

To pass this level, you need to suspend me and launch me again! You can 
background me with Ctrl-Z or, if you're not ready to do that for whatever 
reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~suspending-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running in 
this terminal... Let's check!

UID          PID    PPID  C STIME TTY          TIME CMD
root         146     136  0 16:12 pts/0    00:00:00 bash /challenge/run
root         153     136  0 16:12 pts/0    00:00:00 bash /challenge/run
root         155     153  0 16:12 pts/0    00:00:00 ps -f

Yay, I found another version of me! Here is the flag:
pwn.college{siWJhSryzY-A6XTZgIDoWCzk362.QX1QDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{siWJhSryzY-A6XTZgIDoWCzk362.QX1QDO0wiMyAzNzEzW}

## Challenge 6
**Resuming process**

Process:
use builtin fg command to resume process.

```
hacker@processes~resuming-processes:~$ /challenge/run
Let's practice resuming processes! Suspend me with Ctrl-Z, then resume me with 
the 'fg' command! Or just press Enter to quit me!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~resuming-processes:~$ fg
/challenge/run
I'm back! Here's your flag:
pwn.college{g_IMrcxI33UyviL1Fwv8If8XKh_.QX2QDO0wiMyAzNzEzW}
```
Flag:
>pwn.college{g_IMrcxI33UyviL1Fwv8If8XKh_.QX2QDO0wiMyAzNzEzW}

## Challenge 7
**Backgrounding process**

Process:
use builtin bg command to resume process in background.
```
hacker@processes~backgrounding-processes:~$ /challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         146 S+   bash /challenge/run
root         148 R+   ps -o user=UID,pid,stat,cmd

I don't see a second me!

To pass this level, you need to suspend me, resume the suspended process in the 
background, and then launch a new version of me! You can background me with 
Ctrl-Z (and resume me in the background with 'bg') or, if you're not ready to 
do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~backgrounding-processes:~$ bg
[1]+ /challenge/run &
hacker@processes~backgrounding-processes:~$ 

Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out.
/challenge/run
I'll only give you the flag if there's already another copy of me running *and 
not suspended* in this terminal... Let's check!

UID          PID STAT CMD
root         146 S    bash /challenge/run
root         156 S    sleep 6h
root         157 S+   bash /challenge/run
root         159 R+   ps -o user=UID,pid,stat,cmd

Yay, I found another version of me running in the background! Here is the flag:
pwn.college{kAmlpppg2lcfZiEGESITuTGnQhL.QX3QDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{kAmlpppg2lcfZiEGESITuTGnQhL.QX3QDO0wiMyAzNzEzW}


## Challenge 8
**Foregrounding process**

Process:
use bg first then fg next to get the flag
```
hacker@processes~foregrounding-processes:~$ /challenge/run
To pass this level, you need to suspend me, resume the suspended process in the 
background, and *then* foreground it without re-suspending it! You can 
background me with Ctrl-Z (and resume me in the background with 'bg') or, if 
you're not ready to do that for whatever reason, just hit Enter and I'll exit!
^Z
[1]+  Stopped                 /challenge/run
hacker@processes~foregrounding-processes:~$ bg %1
[1]+ /challenge/run &

Yay, I'm now running the background! Because of that, this text will probably 
overlap weirdly with the shell prompt. Don't panic; just hit Enter a few times 
to scroll this text out. After that, resume me into the foreground with 'fg'; 
I'll wait.

hacker@processes~foregrounding-processes:~$ fg %1
/challenge/run
YES! Great job! I'm now running in the foreground. Hit Enter for your flag!

pwn.college{gfSAvn_iqwdYq_sYiDE8ZFRlfjd.QX4QDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{gfSAvn_iqwdYq_sYiDE8ZFRlfjd.QX4QDO0wiMyAzNzEzW}

## Challenge 9
**Starting background process**

Process:
The & will start the process in the background, which will then print the flag .
```
hacker@processes~starting-backgrounded-processes:~$ /challenge/run &
[1] 146

Yay, you started me in the background! Because of that, this text will probably 
overlap weirdly with the shell prompt, but you're used to that by now...

Anyways! Here is your flag!
pwn.college{sAv5DGBJSRlQrJ3IB9Ae2gscpBg.QX5QDO0wiMyAzNzEzW}
```
Flag:
> pwn.college{sAv5DGBJSRlQrJ3IB9Ae2gscpBg.QX5QDO0wiMyAzNzEzW}

## Challenge 10
**Processing exit codes**

Process:
we can access the exit code of the most recently-terminated command using the special ? variable and prepend it with $ to read its value.
```
hacker@processes~process-exit-codes:~$ /challenge/get-code
Exiting with an error code!
hacker@processes~process-exit-codes:~$ echo $?
70
hacker@processes~process-exit-codes:~$ /challenge/submit-code 70
CORRECT! Here is your flag:
pwn.college{QSzy1hIpRtLEUXwmUIMh48DnZWB.QX5YDO1wiMyAzNzEzW}
```
Flag:
> pwn.college{QSzy1hIpRtLEUXwmUIMh48DnZWB.QX5YDO1wiMyAzNzEzW}

