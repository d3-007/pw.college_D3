# Readirecting output
redirecting standard outputs to a files reqires '>'
```
You have created the COLLEGE file and wrote the right value to it, but it 
doesn't look like you did it via input redirection.
hacker@piping~redirecting-output:~$ echo PWN > COLLEGE
Correct! You successfully redirected 'PWN' to the file 'COLLEGE'! Here is your 
flag:
pwn.college{ckdfqSXg0XADnjnyAW01lYy9ErM.QX0YTN0wiN2QDN3EzW}
```
# Redirecting more outputs 
redirecting files does not solely depend of echo we can also redirect one
file into the other by the same method 
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
[FLAG] pwn.college{kVPdf96uXAvgZ_wiJBpFxnzXjTM.QX1YTN0wiN2QDN3EzW}
```

# piping appending output 
>> can be used redicrect more contnt to the fileinstead
repalcing the file completely
```
hacker@piping~appending-output:~$ cat /challenge/run >> /home/hacker/the-flag
hacker@piping~appending-output:~$ cat /home/hacker/the-flag
 | 
\|/ This is the first half:
 v 
pwn.college{kAQ3T-DlFTFTqjwQpKzyzePzQeO.QX3ATO0wiN2QDN3EzW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
#!/usr/bin/exec-suid -- /bin/bash -p

exec 5>/dev/tty
DIR=$(/bin/dirname ${BASH_SOURCE[0]})
if ! $DIR/chio.py --check_stdout_path /home/hacker/the-flag --chio_info_fd 5 --chio_warn_fd 5 --chio_hint_fd 5 --chio_test_fd 5 --chio_pass_fd 5 --chio_fail_fd 5 --chio_hype_fd 5
then
        #fold -s > /dev/tty <<< "You aren't redirecting stdout to /home/hacker/the-flag! Rerun me with the output redirected (in append mode!)."
        exit 1
fi

fold -s > /dev/tty <<< "I will write the flag in two parts to the file /home/hacker/the-flag! I'll do the first write directly to the file, and the second write, I'll do to stdout (if it's pointing at the file). If you redirect the output in append mode, the second write will append to (rather than overwrite) the first write, and you'll get the whole flag!"

(
        echo " | "
        echo "\\|/ This is the first half:"
```

# redirecting errors 
pwn.college{wDLuob2OylogJoOBcYMfKbtiQoq.QXxcTN0wSOwEzNzEzW}
basically you can use dicrect output into multile files 
> into one and 2> errors into another
0 stands for input , 1 for output and 2 for error


# redirecting inputs 
'<' is used to rediect input into the program, below we met 
certain conditions before we were allowed to dispaly the input 
```
hacker@piping~redirecting-input:~$ echo COLLEGE < PWN
COLLEGE
hacker@piping~redirecting-input:~$ /challenge/run > PWN
hacker@piping~redirecting-input:~$ cat PWN
You have not redirected anything to my standard input. Please do so, using '<'.
hacker@piping~redirecting-input:~$ echo COLLEGE > PWN
hacker@piping~redirecting-input:~$ /challenge/run < PWN
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{Yxe8iYyPY4s9hfT5Vl3aFhueK_F.QXwcTN0wiN2QDN3EzW}
```


# grepping stored results 
```
hacker@piping~grepping-stored-results:~$ /challenge/run > /tmp//data.txt
... ...
hacker@piping~grepping-stored-results:~$ grep "pwn.college" /tmp/data.txt
pwn.college{IZqWMesVewVduyjS9JPkmMZUGXK.QX4EDO0wiN2QDN3EzW}
```
# grepping stored outputs 
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
... ...
pwn.college{srdsjz4KCRuga9X0_V-cOW40ML8.QX5EDO0wiN2QDN3EzW}
```

# Grepping errors 
pipping errors ca not be done directly we need to direct the files 
into another file and then use pipe and grep 
'>&' operator is used to a file disciptor to another file discriptor 
2>& 1- in this all the errors will be stored as a std output 
```
hacker@piping~grepping-live-output:~$ /challenge/run | grep pwn.college
... ...
pwn.college{srdsjz4KCRuga9X0_V-cOW40ML8.QX5EDO0wiN2QDN3EzW}
```
# filtering with grep -v 
grep -v does opposite of grep it displays all the words other than the 
given word 
```
hacker@piping~filtering-with-grep-v:~$ cat /challenge/run | grep -v DECOY
#!/usr/bin/exec-suid -- /bin/bash -p

FLAG=$(cat /flag)
FLAG_CONTENT=$(sed 's/pwn\.college{\(.*\)}/\1/' <<< "$FLAG")

# Generate 1000+ lines with decoys and the real flag
REAL_FLAG_LINE=$((RANDOM % 1000 + 1))

for i in {1..1200}; do
    if [ $i -eq $REAL_FLAG_LINE ]; then
        # Print the real flag
        echo "$FLAG"
    else
        echo -n "pwn.college{"
        echo "}"
    fi
done
hacker@piping~filtering-with-grep-v:~$ echo /challenge/run | grep -v DECOY
/challenge/run
hacker@piping~filtering-with-grep-v:~$ /challenge/run | grep -v DECOY
pwn.college{AWrIyqA8hx7grM4ertxe-RL851U.0FOxEzNxwiN2QDN3EzW}
```


# Filtering with sed 
sed is used to filter or replace remelmsts 
syntax :filenamesed |'s/oldword/newword/g' 
```
hacker@piping~filtering-with-sed:~$ sed 's/FAKEFLAG//g' /challenge/run
#!/usr/bin/exec-suid -- /bin/bash -p

flag=$(cat /flag)

for (( i=0; i<${#flag}; i++ )); do
  echo -n "${flag:$i:1}"
  echo -n ""
done
hacker@piping~filtering-with-sed:~$ echo sed 's/FAKEFLAG//g' /challenge/run
sed s/FAKEFLAG//g /challenge/run
hacker@piping~filtering-with-sed:~$ echo /challenge/run |sed "s/FAKEFLAG//"
/challenge/run
hacker@piping~filtering-with-sed:~$ echo /challenge/run | sed "s/FAKEFLAG//"                
/challenge/run
hacker@piping~filtering-with-sed:~$ /challenge/run | sed "s/FAKEFLAG//"                
pwFAKEFLAGnFAKEFLAG.FAKEFLAGcFAKEFLAGoFAKEFLAGlFAKEFLAGlFAKEFLAGeFAKEFLAGgFAKEFLAGeFAKEFLAG{FAKEFLAGUFAKEFLAGlFAKEFLAGpFAKEFLAG_FAKEFLAGrFAKEFLAGBFAKEFLAGaFAKEFLAGbFAKEFLAGkFAKEFLAGkFAKEFLAGuFAKEFLAGCFAKEFLAGUFAKEFLAGYFAKEFLAGZFAKEFLAGBFAKEFLAGVFAKEFLAGDFAKEFLAGDFAKEFLAGTFAKEFLAGBFAKEFLAGiFAKEFLAGwFAKEFLAGhFAKEFLAGBFAKEFLAG1FAKEFLAGTFAKEFLAG.FAKEFLAG0FAKEFLAG1FAKEFLAGNFAKEFLAGxFAKEFLAGQFAKEFLAGTFAKEFLAGMFAKEFLAGyFAKEFLAGwFAKEFLAGiFAKEFLAGNFAKEFLAG2FAKEFLAGQFAKEFLAGDFAKEFLAGNFAKEFLAG3FAKEFLAGEFAKEFLAGzFAKEFLAGWFAKEFLAG}FAKEFLAGhacker@piping~filtering-with-sed:~$ /challenge/run | sed 's/FAKEFLAG//g'                
pwn.college{Ulp_rBabkkuCUYZBVDDTBiwhB1T.01NxQTMywiN2QDN3EzW}ha

```

