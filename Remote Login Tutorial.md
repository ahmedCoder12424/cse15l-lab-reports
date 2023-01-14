# Remote Login Instructions 

1. __Find CSE15l account__

Go to this [link](https://sdacs.ucsd.edu/~icc/index.php) and look up your account entering your username and PID.

2. __Change Password__

After finding your cse15l account click on it to change the password. When it asks for your username and PID again, __ENTER YOUR CSE15L USERNAME NOT YOUR GENERAL USERNAME__.
After doing so, change your password. __Make sure to select NO__ for changing general Triton link account's password.

![Image](https://github.com/ahmedCoder12424/cse15l-lab-reports/blob/main/step1.png)

3. __Wait__ 

Wait for the password reset to take place. It may take 15 min to a day.

4. __Open Terminal on VScode__

Click on Terminal on VScode and select new Terminal to open up a new terminal.

5. __Login on VScode Terminal__

To login, in the terminal, type in `ssh cse15lwi23zzz`. zzz is your specific letter sequence in your account.
Enter your password after being prompted to do so.

![Image](https://github.com/ahmedCoder12424/cse15l-lab-reports/blob/main/step2.png)

6. __Run some commands__ 

Finally, run the following commands to test your remote login.

* cd ~
* cd
* ls -lat
* ls -a
* ls <directory> where <directory> is /home/linux/ieng6/cs15lwi23/cs15lwi23abc, where the abc is one of the other group members’ username
* cp /home/linux/ieng6/cs15lwi23/public/hello.txt ~/
* cat /home/linux/ieng6/cs15lwi23/public/hello.txt

![Image](https://github.com/ahmedCoder12424/cse15l-lab-reports/blob/main/step3.png)
