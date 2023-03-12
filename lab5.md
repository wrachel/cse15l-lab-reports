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
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore
sed -i '43s/index1 += 1;/index2 += 1;/g' ListExamples.java
javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java
java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore
git add ListExample.java
git commit -m "fixed"
git push
```
