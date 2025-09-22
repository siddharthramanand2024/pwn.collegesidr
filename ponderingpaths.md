# Module 2: [Pondering Paths]


##  Challenge 1 
 [**Start the challenge, launch a terminal, invoke the pwn program using its absolute path, and Capture that Flag**]


## Process

use $ / (root) command in the terminal to obtain the flag.

$ /pwn
BOOM!!!
Here is your flag:
pwn.college{cqklbmWk4AfprWlkUlGX-teVsIn.QX4cTO0wiMyAzNzEzW}


## 🏁 Flag

pwn.college{cqklbmWk4AfprWlkUlGX-teVsIn.QX4cTO0wiMyAzNzEzW}


##  Challenge 2 

 [**This challenge again requires you to execute it by invoking its absolute path. You'll want to execute the run file that is in the challenge directory that is, in turn, in the / directory.**]


# Process

using root directory we go into the challenge directory and access run.

$ /challenge/run
Correct!!!
/challenge/run is an absolute path! Here is your flag:
pwn.college{sF5tND3Xek5BIWDRIY-43oaU9i9.QX1QTN0wiMyAzNzEzW}


## 🏁 Flag
pwn.college{sF5tND3Xek5BIWDRIY-43oaU9i9.QX1QTN0wiMyAzNzEzW}


##  Challenge 3

[ **This challenge will require you to execute the /challenge/run program from a specific path (which it will tell you). You'll need to cd to that directory before rerunning the challenge program.** ]


# Process

first we find the correct directory

/challenge$ /challenge/run
Incorrect...
You are not currently in the /usr/share/doc/fontconfig directory.
Please use the `cd` utility to change directory appropriately.


then we go to the correct directory using cd and then run it.


/usr/share/doc/fontconfig$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{Q0BQEi6mfJevxd9jbb591Tiznlz.QX2QTN0wiMyAzNzEzW}


## 🏁 Flag
pwn.college{Q0BQEi6mfJevxd9jbb591Tiznlz.QX2QTN0wiMyAzNzEzW}

note: challenge 4 and 5 is the same as 3 .. just using cd to find the paths so  directly writing the flags..
flag 4:pwn.college{QXSCU_8qxO33qxw2DxIW2ZzhZBP.QX3QTN0wiMyAzNzEzW}
flag 5:pwn.college{8gBk2jLfkJN2-uclJ3rbgO7iKUa.QX4QTN0wiMyAzNzEzW}

##  Challenge 6 
 [**You'll need to run /challenge/run using a relative path while having a current working directory of /. For this level, I'll give you a hint. Your relative path starts with the letter c**]


## Process

since it starts with c challenge is starting of the relative path.

$ challenge/run
Correct!!!
challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{06DNwyVTAWL8MJMDAVG7-AkZp5A.QX5QTN0wiMyAzNzEzW}


## 🏁 Flag
pwn.college{06DNwyVTAWL8MJMDAVG7-AkZp5A.QX5QTN0wiMyAzNzEzW}


## Challenge 7
[** This challenge will get you using . in your relative paths. Get ready!**]

## Process
using .(relative path) to access

/$ ./challenge/run
Correct!!!
./challenge/run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{AE_sMMjxy3kmp6uV5qtqYMpyIX3.QXwUTN0wiMyAzNzEzW}

## 🏁 Flag
pwn.college{AE_sMMjxy3kmp6uV5qtqYMpyIX3.QXwUTN0wiMyAzNzEzW}


## Challenge 8
[** The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using . like in the previous levels. Give it a try now!**]

## Process
using .(relative path) to access

$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{Ibrgw0zkCBj-jk4OeF2oWz9K5PV.QXxUTN0wiMyAzNzEzW}

## 🏁 Flag
pwn.college{Ibrgw0zkCBj-jk4OeF2oWz9K5PV.QXxUTN0wiMyAzNzEzW}



## Challenge 9
[** Now it's your turn to play! In this challenge, /challenge/run will write a copy of the flag to any file you specify as an argument on the commandline, with these constraints:

Your argument must be an absolute path.
The path must be inside your home directory.
Before expansion, your argument must be three characters or less.**]

## Process
Run the  program with ~/a as the argument. This  creates a file named a in  home directory and gives us the flag.

$ /challenge/run ~/a
Writing the file to /home/hacker/a!
... and reading it back to you:
pwn.college{AOBKfipznCAJHc2erR-Z3OBdRaW.QXzMDO0wiMyAzNzEzW}

## 🏁 Flag
{AOBKfipznCAJHc2erR-Z3OBdRaW.QXzMDO0wiMyAzNzEzW}
