# Position thy self
The challenge requires you to navigate trough files by using the keyword cd as a command and passing a path as its argument.
The challenge asks you to find a path of a file 

## My Solve
**Flag:** 'pwn.college{I9oEgY6DLf3eShPVOK3-vM5lsIg.QX4cTO0wSOwEzNzEzW}'


```
hacker@paths~position-thy-self:~$ /challenge/run
Incorrect...
You are not currently in the / directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~position-thy-self:~$ cd /directory
bash: cd: /directory: No such file or directory
hacker@paths~position-thy-self:~$ cd /
hacker@paths~position-thy-self:/$ /challenge/run
Correct!!!
/challenge/run is an absolute path, invoked from the right directory!
Here is your flag:
pwn.college{sbeVdvgGvravM1SbZKSSka7BtML.QX2QTN0wSOwEzNzEzW}
```

## What I Learned
The correct directory was given in the challenge instructions when you run /challenge/run from the wrong location.
The given file was in the /direcotry file and i had to change the path of the directory by passing a command cd and argument / which took the control line to home page from where the files was accessed.
/challenge/run is an absolute path, invoked from the right directory after changing the directory.
## References
None.
'
