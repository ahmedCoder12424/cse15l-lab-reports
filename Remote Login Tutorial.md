# VScode/Remote Login Set Up Instructions 

1) __Install VScode__

Install vscode with this [link](https://code.visualstudio.com/).

I didn't need to do this step because I had it installed alreadly.

2) __Find CSE15l account__

Go to this [link](https://sdacs.ucsd.edu/~icc/index.php) and look up your account entering your username and PID.

3) __Change Password__

After finding your cse15l account click on it to change the password. When it asks for your username and PID again, __ENTER YOUR CSE15L USERNAME NOT YOUR GENERAL USERNAME__.
After doing so, change your password. __Make sure to select NO__ for changing general Triton link account's password.

![Image](step1.png)



4) __Wait__ 

Wait for the password reset to take place. It may take 15 min to a day.

5) __Open Terminal on VScode__

Click on Terminal on VScode and select new Terminal to open up a new terminal.

6) __Login on VScode Terminal__

To login, in the terminal, type in `ssh cse15lwi23zzz`. zzz is your specific letter sequence in your account.
Enter your password after being prompted to do so.

![Image](step2.png)

7) __Run some commands__ 

Finally, run the following commands to test your remote login.

* `cd ~`
* `cd`
* `ls -lat`
* `ls -a`
* `ls <directory>` where `<directory>` is `/home/linux/ieng6/cs15lwi23/cs15lwi23abc`, where the abc is one of the other group members’ username
* `cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/`
* `cat /home/linux/ieng6/cs15lwi23/public/hello.txt`

The `cd` command changes directory and two commands show run without error. The `ls` command lists files in a certain directory and show different files for each of three `ls` commands shown. The `cp` command copies the file `hello.txt`. Lastly, the `cat` shows the contents of the `hello.txt` file.

![Image](step3.png)
