# Implicit relative paths
This challenge requires you to access files using . 
## My Solve
**Flag:** 'pwn.college{4plPZvaJz93kK-RcCxscELgZOjE.QXxUTN0wSOwEzNzEzW}'

```
hacker@paths~implicit-relative-path:~$ /challenge/run
Incorrect...
You are not currently in the /challenge directory.
Please use the `cd` utility to change directory appropriately.
hacker@paths~implicit-relative-path:~$ cd /
hacker@paths~implicit-relative-path:/$ cd /challenge
hacker@paths~implicit-relative-path:/challenge$ ./run
Correct!!!
./run is a relative path, invoked from the right directory!
Here is your flag:
pwn.college{4plPZvaJz93kK-RcCxscELgZOjE.QXxUTN0wSOwEzNzEzW}

```

## What I Learned
Every every directory has implicit entries that you can reference in paths: . ,refers right to the same directory
I learned how to explicitly use relative paths to access a  path. The way to do this is to tell Linux that you explicitly want to execute a program in the current directory, using .
./run is a relative path, invoked from the right directory

## References
None.
