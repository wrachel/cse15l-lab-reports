# Lab Report 5

In this lab report, I will be describing how I completed Lab Report 4, as well as how I could write a bash script to finish the task even faster.

In lab report 4, I did not use a bash script and attempted to type out the commands to complete 
the tasks as fast as possible. This meant I was copy-pasting from my browser, using tab to autocomplete, and using the up/down arrows to get previous commands. 

One way I could complete the steps even faster is to put the commands into a bash script.

The following commands below are the commands I used to finish the tasks:
```
ssh cs15lwi23aup@ieng6.ucsd.edu
git clone git@github.com:wrachel/lab7.git
cd lab7
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTest
sed -i '43s/index1 += 1;/index2 += 1;/g' ListExamples.java
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTest
git add ListExamples.java
git commit -m "fixed"
git push
```

NOTE: in the original lab, I did not use the command `sed -i '43s/index1 += 1;/index2 += 1;/g' ListExamples.java`. Instead, I used nano to open the file and then edited the file using nano. However, since I could not do this in a bash script, I used the `sed` command to edit line 43 (the location in the file that was causing the error), and edited the line so that it would no longer cause an error. 

If I were to put these commands in a bash file, the output would look like the screenshots below:

![image](https://user-images.githubusercontent.com/40574565/224580110-ccd8b968-fec7-42a2-b28f-85fd368b95d9.png)
![image](https://user-images.githubusercontent.com/40574565/224580124-db76917a-19d3-4738-aca5-a67b13427932.png)

This is what the bash file looks like:
![image](https://user-images.githubusercontent.com/40574565/224580135-cba485b4-df1d-4885-a5c5-70f6bb5ca05e.png)

The file does not contain the `ssh` command, as I first ssh into the remote device and then create a bash file that contains the other commands. 

This would be how I could streamline completing all the tasks using a bash file, and would be much faster than typing out all the commands by hand everytime.


