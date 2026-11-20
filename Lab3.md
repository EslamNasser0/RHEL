# Lab 3

lab record
[![asciicast](assets/lab3.png)](https://asciinema.org/a/4gD1BXOEQ3hccV22?autoplay=1&loop=1&speed=2)

## Read the file `/etc/passwd` and notice the different fields. 
``` bash
cat /etc/passwd

# Extract your info from it
cat /etc/passwd | grep eslam
```

## What is the different between cat and more command

``` bash
# cat used to concatinate text files and display it
echo hi from file1 > file1
echo hi from file2 > file2
cat file1 file2

# more used to display text files
more /etc/passwd 
```

## What is the difference between rm and rmdir using man? 
``` bash
man rm; man rmdir
```

## Create the following hierarchy
![lab1 hierarchy](assets/lab1%20hierarchy.png)

``` bash
mkdir -p ./dir1/dir11 ./dir1/dir12 ./mydocs
touch ./dir1/dir11/file
touch ./mydocs/mycv

# Remove dir11 in one step. What do you notice? And how to overcome that?
rm -fr ./dir1/dir11

# Then remove dir12 using rmdir –p command. State what happened to the hierarchy (Note: you are in your home dir).
rmdir –p ./dir1/dir12
```

### The output of the command `pwd` was `/home/myuser`.Write the absolute and relative path for the file mycv
``` bash
tree
# absolute /home/eslamnasser/mydocs/mycv
# relative ./mydocs/mycv
```

## You are in /usr/bin, list four ways to go to your home directory
``` bash
cd /usr/bin

# 1
cd -
cd /usr/bin

# 2
cd ~
cd /usr/bin

# 3
cd /home/eslamnasser
cd /usr/bin

# 4
cd ../../home/eslamnasser
```

## Copy the `passwd` file to your home directory making its name is mypasswd
``` bash
cp /etc/passwd mypasswd

# Rename this new file to be oldpasswd
mv mypasswd oldpasswd
```

# List Linux commands in `/usr/bin` that start with letter “w”
``` bash
ls /usr/bin | grep -i '^w'
```

# Display the first 4 lines of /etc/passwd
``` bash
head -4 /etc/passwd
```

# Display the last 7 lines of /etc/passwd
``` bash
tail -7 /etc/passwd
```

# Display the users who are logged now to the system
``` bash
w
```

# Display the man pages of passwd the command and the file sequentially in one command
``` bash
man -k '^passwd'
```

# Display the man page of the passwd file
``` bash
man 5 passwd
```

# Display a list of all the commands that contain the keyword passwd in their man page
``` bash
man -a passwd
```
