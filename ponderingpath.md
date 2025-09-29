# Module 14: Pondering Path

## Challenge 1
**Path variable**

Process:
we empty the path so that challenge does not find rm command and get the flag.
```
hacker@path~the-path-variable:~$ PATH=                             
hacker@path~the-path-variable:~$ /challenge/run
Trying to remove /flag...
/challenge/run: line 4: rm: No such file or directory
The flag is still there! I might as well give it to you!
pwn.college{8y2vpqj2sXLSv1XeKRIpChwnQxE.QX2cDM1wiMyAzNzEzW}
```
Flag:
> pwn.college{8y2vpqj2sXLSv1XeKRIpChwnQxE.QX2cDM1wiMyAzNzEzW}

## Challenge 2
**Setting path**

Process:
we can set path to access programs directly.

```
hacker@path~setting-path:~$ PATH=/challenge/more_commands/
hacker@path~setting-path:~$ /challenge/run
Invoking 'win'....
Congratulations! You properly set the flag and 'win' has launched!
pwn.college{kH1UidhMNDtJYNVDoNXeMwbOh7t.QX1cjM1wiMyAzNzEzW}
```
Flag:
> pwn.college{kH1UidhMNDtJYNVDoNXeMwbOh7t.QX1cjM1wiMyAzNzEzW}

## Challenge 3
**Finding commands**

Process:
we can find files using which command
```
hacker@path~finding-commands:~$ which win
/challenge/paths/11326/win
hacker@path~finding-commands:~$ cat /challenge/paths/11326/flag
pwn.college{4zuDJyZz2gQmML205YEaHS1MY9b.01NzEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{4zuDJyZz2gQmML205YEaHS1MY9b.01NzEzNxwiMyAzNzEzW}

## Challenge 4
**Creating commands**

Process:
```
hacker@path~adding-commands:~$ mkdir -p ~/mybin
cat > ~/mybin/win <<'EOF'
chmod +x ~/mybin/win
export PATH="$HOME/mybin:$PATH"
/challenge/run
Invoking 'win'....
pwn.college{8r7rqX5NZDr1EQm_qZhyVFY6PH8.QX2cjM1wiMyAzNzEzW}
```
Flag:
> pwn.college{8r7rqX5NZDr1EQm_qZhyVFY6PH8.QX2cjM1wiMyAzNzEzW}

## Challenge 5
**Hijacking commands**

Process:
```
hacker@path~hijacking-commands:~$ mkdir -p ~/mybin
cat > ~/mybin/rm <<'EOF'
chmod +x ~/mybin/rm
export PATH="$HOME/mybin:$PATH"
which rm
cat /tmp/flag.saved
/home/hacker/mybin/rm
Trying to remove /flag...
Found 'rm' command at /home/hacker/mybin/rm. Executing!
pwn.college{Q3CpGPChmh_pOr5Yu49qDnpzx_t.QX3cjM1wiMyAzNzEzW}
```
Flag:
> pwn.college{Q3CpGPChmh_pOr5Yu49qDnpzx_t.QX3cjM1wiMyAzNzEzW}
