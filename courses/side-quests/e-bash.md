#Bash (and Linux command lines)

#Outcome

You'll understand what bash is, and how to use it.

#Advice

Bash is a pretty clunky old technology. But it has the benefit of coming in OSX / Linux natively.

##What is it

Your command line (iterm) is bash. Bash is a 'shell' (interactive command line). There are different shells, bash (bourne shell), ksh (korn shell) etc. Bash is also a programming language, which you are using interactively on the command line. It supports almost everything Javascript supports, it's just horrible.

##Why use it

It's native on most machines, so rather than installing node + npm, you can just get things done in it right off the bat. So if you need a script to install stuff to run your program - bash is a good option.

##Using it interactively on the command line

OSX comes with bash by default, so you've already been using it every time you run an iterm.

##Bash scripts

By convention bash scripts end in `.sh`. e.g. `run.sh` (`.sh` stands for shell). You can then just fill the file with commands you could type on the command line. If you're running bash (you are by default by running iterm2), if you execute the script then it will guess that it's bash. If somebody changes their default 'shell' then it will try to run it in that shell. e.g korn shell. You're script might then not work.

If you execute a script natively on the command line. The first line of the script can be used to tell linux which language it's in. e.g. `#!/bin/bash` -> Tells it it's a bash script. Could also be a ksh, python script or something else.

##File permissions and chmod

To execute a script you must make sure it's executable. You can do this by using the `chmod` command. e.g. `chmod u+x`. You can check permissions using `ls -ltr`. Once the script is executable you can execute by doing `path/to/script.sh` on the command line. If you're in the same folder you must do `./script.sh`. `script.sh` will not work (I don't know why).


##Bash syntax

Is awful. I find it really hard. Try to avoid writing complex scripts, I find if statements a struggle. Bash is sensitive to spaces. Equality is a joke. Try and use it simply when you can :).

###Comments

`# Commenting goes here`

###Variables

####Declare

`MY_VAR="value" #Spaces aren't allowed...`

####Usage

`echo $MY_VAR #Notice the $`

### &&

`command1 && command2 #command2 only happens if command1 succeeds.`

'Succeeds' is determined by exit code / return code. 0 means success. anything else means failure (different numbers mean different things). This is brought over from C programming.

###If statements

Google it. Spaces matter.

##Environment Variables

Think of interactive bash like the console in javascript. You're commands into an interactive bash programming console.

Environment variables are variables which are set by default in bash. You can modify them both temporarily and permanently.

For example `$JAVA_HOME` is a variable used to tell the OS where Java is installed. You can change it temporarily (just for this bash instance) or forever (future bash sessions).

You set them the same as you set variables (because they are variables). You can see them all with `printenv`.

###The PATH

`PATH` is a special environment variable. It's a string of colon seperated folders. e.g. `/Users/richard/.nvm/versions/node/v4.2.2/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin`. Any executable (`chmod u+x`) programs in these folders, you can execute from anywhere in bash by typing the name of the script / program. E.g. `ls`, `node`, `npm`.

Most things modify the PATH for you, or put a 'link' to the program in the correct folder. So when you brew install things, it's handling this for you :).

##Useful things you can do:

[See cheatsheet](../../resources/bash-cheat-sheet.md)

#Tasks

* Make a bash script which prints hello to screen. And run it.
