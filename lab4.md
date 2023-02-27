# Lab Report 4

In this lab report, I will be explaining how I completed steps 4-9 in the lab with the fastest time I could achieve. 

### Step 4: Log into ieng6
Keys pressed: ```ssh cs15lwi23aup@ieng6.ucsd.edu <enter>```

![image](https://user-images.githubusercontent.com/40574565/221509969-dcec8f6c-fdbd-4f4a-a379-8bb61064b2e5.png)

I had the command `ssh cs15lwi23aup@ieng6.ucsd.edu` already typed into the terminal, so all I had to do was press enter (since the timer only starts once enter is pressed). 
When I pressed enter I did not have to type in my password since previously, I copied the public ssh key from my local computer to the remote account. This makes it faster, since everytimg I log in I no longer have to type a password everytime I use ssh to access the remote computer. 

### Step 5: Clone your fork of the repository from your Github account
Keys pressed: ```git clone``` ```<Ctrl-C><left click on terminal><Ctrl-V><enter>```
![image](https://user-images.githubusercontent.com/40574565/221512230-cc31ba29-4d12-4239-95dd-9aebbbb3cdad.png)

I had used ```<Ctrl-C>``` to copy `git@github.com:wrachel/lab7.git`. I got this from my forked repository (depicted below).

![image](https://user-images.githubusercontent.com/40574565/221512405-b9758a24-f6b0-428b-bada-643656f8c18d.png)

I have previously generated SSH keys for Github. The below image shows how the SSH key has been added to my github. This allows me to clone and commit to a repository from the remote computer. 

![image](https://user-images.githubusercontent.com/40574565/221512868-39d990e1-1058-4356-becc-5e632be3850c.png)

### Step 6: Run the tests, demonstrating that they fail
Keys pressed: 
```cd l<tab>```
```<left click on local device><Ctrl-C><left click on terminal><Ctrl-V><enter>``` 
```<left click on local device><Ctrl-C><left click on terminal><Ctrl-V><enter>```

![image](https://user-images.githubusercontent.com/40574565/221515929-773c51ca-662c-45a0-978d-3ad0463dbfcb.png)

In the first command, the tab autocompletes to lab7. This command changes the directory to lab7. 
In the second command, I copied `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` from my local device and pasted it onto the terminal using `<Ctrl-V>`.
In the third command, I copied `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` from my local device and pasted it onto the terminal using `<Ctrl-V>`.

### Step 7: Edit the code file to fix the failing test
Keys pressed:
```nano L<tab>.j<tab><enter>```

![image](https://user-images.githubusercontent.com/40574565/221517530-54398f6f-0cb4-4ddf-97e5-80350150e82b.png)

Keys pressed: ```<down arrow (held down arrow until I reached the desired line)><left arrow><backspace><2><Ctrl-X><y><enter>```

![image](https://user-images.githubusercontent.com/40574565/221517195-e6912c0c-8646-49dc-befb-e35129a0a8de.png)

In the first command, the first tab autocompletes to ListExamples, and the 2nd tab autocompletes to java. After entering this command, I enter the file and press down arrow until I reach the line that needs to be changed. Then I press the left arrow until I reach the end of the word `index1`, and press backspace to replace the one with a 2. Then to save the changes, I press `<Ctrl-X>`, and confirm I would like to save the changes to the current file.

### Step 8: Run the tests, demonstrating that they now succeed
Keys pressed:

```<up><up><up><enter>```
```<up><up><up><enter>```

![image](https://user-images.githubusercontent.com/40574565/221518730-0cfda26a-4aa7-4b87-8787-5e0568da02b7.png)

The `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` was 3 up in my search history, so I pressed the up arrow 3 times to access it.

The `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTest` was 3 up in my search history, so I pressed the up arrow 3 times to access it.


### Step 9: Commit and push the resulting change to your Github account (you can pick any commit message!)

```git add L<tab>.j<tab><enter>```
```git commit -m "fixed" <enter>```
```git push <enter>```

![image](https://user-images.githubusercontent.com/40574565/221520335-2105caba-c3c2-473d-8d40-e165d8fad657.png)

In the first command, the first tab autocompletes to ListExample and the second tab autocompletes to .java so that the final command is `git add ListExample.java`. This adds the changes I made in ListExample.java to be committed. 

In the second command, I typed out `git commit -m "fixed"` so that the commit message is "fixed".

In  the third command, I pushed my changes to the git repository using `git push`

