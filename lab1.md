# Lab Report 1

This lab report details how to install VScode and remotely connect through ssh using a unique individual email.

## Installing VScode
I already had VScode installed from a previous course. I opened a new window and included a screenshot to show that VScode is downloaded.
![image](https://user-images.githubusercontent.com/40574565/212200682-ea5b093d-5db3-4f5a-90a4-8351ab66ca7b.png)
For future reference, in order to download VScode, go to the Visual Studio Code website and download onto Windows system: [https://code.visualstudio.com/](https://code.visualstudio.com/).
At the VSCode website, click donwload for the correct OS System. For example, for Windows OS, click Windows. For Mac OS, click macOS.
![image](https://user-images.githubusercontent.com/40574565/215368551-96e96f06-22bb-498f-8dae-092ef74bc297.png)



## Remotely Connecting

### Find individual account
I found my individual account on [this website](https://sdacs.ucsd.edu/~icc/index.php). I put my username (used for ucsd), and student ID, which returned a unique account `cs15lwi23xxx` where xxx is 3 unique letters.
![image](https://user-images.githubusercontent.com/40574565/212200501-0bf06847-ea46-48dc-8f98-b7c3cc7a7771.png)

### Connect in VSCode
Open in VSCode terminal. Make sure terminal is set to bash. In order to do this, search `Terminal: Select Default Profile` and set it to Bash. 

In VSCode terminal, type `ssh cs15lwi23xxx@ieng6.ucsd.edu` where xxx is the same 3 unique letters given earlier. After putting this in the terminal, the output should look like the screenshot below. 
![image](https://user-images.githubusercontent.com/40574565/215428397-fc003736-63ad-4e1f-a51d-fe99ce46c0b8.png)
After logging in, the terminal will display information such as the last login time, which server (e.g. ieng6-202.ucsd.edu) the user was logged into, the CPU usage on the system. This screenshot includes a network delay issue causing slowness on the system. This is purely a notice and shouldn't significantly affect the user.

If it is the users' first tie logging in in awhile, it may shows some notices after logging in (displayed in the iage below). The notice explains that `Authorized use of this system is limited to password-authenticated usernames which are issued to individuals and are for the sole use of the person to whom they are issued....`. These notices are displayed when a user ssh's in if they have not logged in for awhile, and can largely be ignored.  
![image](https://user-images.githubusercontent.com/40574565/212201442-09546375-bafc-49a6-bad9-6771f58772d4.png)
* special note, when typing in the password nothing will show up on the screen for privacy reasons to hide the password.

## Trying Some Commands
After logging in through ssh, I tested some commands:
```java
ls //lists all the files in the current directory
cd ~  //changes the director to the home directory
ls -a //lists all files, including hidden files, in the current directory
pwd //prints the working directory
```

First, I typed `ls` to list all the directories, and found that there were many directories for all the individual accounts. 
![image](https://user-images.githubusercontent.com/40574565/215430115-ada8db02-fd5a-4516-9da9-ad48f660ef49.png)

In order to access my home directory, I typed in the command `cd ~`.  
I then typed in the command `ls -a`, which lists all files, including hidden ones. This is why additional files, like .bash_profile can be seen. 
I typed the command pwd to print the working directory, and confirmed I was in my home directory.
![image](https://user-images.githubusercontent.com/40574565/215430193-60667549-91e4-464e-ad8a-df964bf5a059.png)






