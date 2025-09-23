# The Root
The challenge asks you to find a path of a file 
## My Solve
**Flag:** 'pwn.college{I9oEgY6DLf3eShPVOK3-vM5lsIg.QX4cTO0wSOwEzNzEzW}'

1st we execute type '/' which is the root of the filesystem, then we invoked a file called pwn to complete the challenge 

```
hacker@paths~the-root:~$ /
bash: /: Is a directory
hacker@paths~the-root:~$ /pwn
BOOM!!!
Here is your flag:
pwn.college{I9oEgY6DLf3eShPVOK3-vM5lsIg.QX4cTO0wSOwEzNzEzW}
```

## What I Learned
I learnt how to invoke a program by providing its path on the shell.
The style of path, one that starts with the root directory '/', is referred to as an "absolute path".

## References
None.
