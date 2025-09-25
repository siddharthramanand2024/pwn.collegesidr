# Module 8: Data Manipulation


##  Challenge 1 
 **Translating characters**

Process:
we can use tr command to replace one character with another.
in this challenge we have to convert lowercase to uppercase and vice versa.
this can be done by command chaining which is very interesting along with obviously piping.
```
hacker@data~translating-characters:~$ /challenge/run
Your case-swapped flag:
PWN.COLLEGE{KnPEzdAsW1SHvby53uidlvKxkeD.01mXeZnXWImYaZnZeZw}

hacker@data~translating-characters:~$ /challenge/run | tr 'a-zA-Z' 'A-Za-z'
yOUR CASE-SWAPPED FLAG:
pwn.college{kNpeZDaSw1shVBY53UIDLVkXKEd.01MxEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{kNpeZDaSw1shVBY53UIDLVkXKEd.01MxEzNxwiMyAzNzEzW}

##  Challenge 2 
 **Deleting characters**

Process:
we can use tr command to also delete characters using the -d flag.
in this challenge we have to delete ^ and %.

```
hacker@data~deleting-characters:~$ /challenge/run | tr -d '^%'
Your character-stuffed flag:
pwn.college{QvOqKPcGcnGJdml4IGO8mwqz70z.0FNxEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{QvOqKPcGcnGJdml4IGO8mwqz70z.0FNxEzNxwiMyAzNzEzW}

##  Challenge 3 
 **Deleting newlines**

Process:
we can solve this by piping the output to tr and telling it to delete the newline character,which is represented by the escape sequence \n.
```
hacker@data~deleting-newlines:~$ /challenge/run | tr -d '\n'
Your line-split flag: pwn.college{0NkVatkDVHevCk57aX6SXAY9mw7.0VNxEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{0NkVatkDVHevCk57aX6SXAY9mw7.0VNxEzNxwiMyAzNzEzW}

##  Challenge 4
 **Extracting lines with head**

Process:
we can extract the first n lines with head using the head -n command.
here we have to extract first 7 lines and pipe them.
```
hacker@data~extracting-the-first-lines-with-head:~$ /challenge/pwn | head -n 7 | /challenge/college
Congratulations, you piped the right codes!
pwn.college{gTjJ1O0z1FLnqy44jeeaoK283im.0lNxEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{gTjJ1O0z1FLnqy44jeeaoK283im.0lNxEzNxwiMyAzNzEzW}

##  Challenge 5
 **Extracting columns*

Process:
we can extract the columns using the cut-d command.
we have to use cut and tr in tandem to get the final flag.
```
hacker@data~extracting-specific-sections-of-text:~$ /challenge/run | cut -d ' ' -f2 | tr -d '\n'
pwn.college{kOXi-lA8JHdnqL_YFUri-5Lwzch.01NxEzNxwiMyAzNzEzW}
```
Flag:
> pwn.college{kOXi-lA8JHdnqL_YFUri-5Lwzch.01NxEzNxwiMyAzNzEzW}

##  Challenge 6
 **Sorting data*

Process:
we can sort the data using the sort command.
by default it sorts acc to ascending order.
this challenge requires descending order so we pass sort along with the argument r to get the flag.
```
hacker@data~sorting-data:~$ sort /challenge/flags.txt -r
pwn.college{0jPYj-jmm1O-UhSJo8qebaksn_G.0FM0MDOxwiMyAzNzEzW}
```
Flag:
> pwn.college{0jPYj-jmm1O-UhSJo8qebaksn_G.0FM0MDOxwiMyAzNzEzW}


