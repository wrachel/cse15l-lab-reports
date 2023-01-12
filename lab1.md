{% include navigation.html %}

# Lab Report 1

This lab report details how to install VScode and remotely connect through ssh using a unique individual email.

## Installing VScode
I already had VScode installed from a previous course. I opened a new window and included a screenshot to show that VScode is downloaded.
![image](https://user-images.githubusercontent.com/40574565/212200682-ea5b093d-5db3-4f5a-90a4-8351ab66ca7b.png)
For future reference, in order to download VScode, go to the Visual Studio Code website and download onto Windows system. 

## Remotely Connecting

### Find individual account
I found my individual account on [this website](https://sdacs.ucsd.edu/~icc/index.php). I put my username (used for ucsd), and student ID, which returned a unique account `cs15lwi23xxx` where xxx is 3 unique letters.
![image](https://user-images.githubusercontent.com/40574565/212200501-0bf06847-ea46-48dc-8f98-b7c3cc7a7771.png)

### Connect in VSCode
Open in VSCode terminal. Make sure terminal is set to bash. In order to do this, search `Terminal: Select Default Profile` and set it to Bash. 

In VSCode terminal, type `ssh cs15lwi23xxx@ieng6.ucsd.edu` where xxx is the same 3 unique letters given earlier. After putting this in the terminal, the output should look like the screenshot below. It shows some notices, etc. once logged in.
![image](https://user-images.githubusercontent.com/40574565/212201442-09546375-bafc-49a6-bad9-6771f58772d4.png)
* special note, when typing in the password nothing will show up on the screen for privacy reasons to hide the password.

## Trying Some Commands
After logging in through ssh, I tested some commands.
First, I typed `ls` to list all the directories, and found that there were many directories for all the individual accounts. In order to access my home directory, I typed in the command `cd ~`. Again, I typed `ls` to see the files in that directory and only found perl5. 

I then typed in the command `ls -a`, which lists all files, including hidden ones. This is why additional files, like .bash_profile can be seen. 
![image](https://user-images.githubusercontent.com/40574565/212201884-79c3025d-5251-4c18-9657-b4310fd2f703.png)





