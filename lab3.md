# Lab 3

### Exploring 'find'

In this lab, I will be exploring the different command-line options for the command `find`

A little information about find:
find searches the directory tree starting from the working directory (or directory specified), and can be used to find files based on certain conditions (e.g. file name, content, etc.)
[source](https://man7.org/linux/man-pages/man1/find.1.html) [source](https://www.tecmint.com/35-practical-examples-of-linux-find-command/#:~:text=The%20find%20command%20is%20used,size%2C%20and%20other%20possible%20criteria.)

# -name
-name finds files based on the file's name
Example 1: 

**COMMAND:**
```
find . -name "P*.txt"
```

**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218356515-c7a95b03-64db-427c-aa20-0eef66445470.png)

**Explanation**
In this command, the find searches through '.' or the current working directory (in this example, the image containing the output also lists the working directory for reference). Then, the `-name` command searches through the file names, and returns all file-names that match the condition "P*.txt", or all txt files that start with a P. This command is useful for someone who would want to find a specific file within their file directory that starts with a certain letter (e.g. if they forgot the name of the file, but only remembered the first letter). This would be espeically helpful for someone with a lot of files, where it would be too tiring to search through all the files by hand. 

[source](https://www.tecmint.com/35-practical-examples-of-linux-find-command/#:~:text=The%20find%20command%20is%20used,size%2C%20and%20other%20possible%20criteria.)

Example 2:

**COMMAND:**
```
find non-fiction -name "*.txt"
```

**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218356665-2768828e-340a-4c87-ac83-aa016f749e10.png)

**Explanation**
In this command, the find searches through the directory `non-fiction` from the working directory (currently in `written_2`). The `-name` command-line argument searches through all the file names that match the condition `*.txt`, or files that end with .txt.  This would be helpful for someone who would want to find all files that contain .txt in its name (e.g. txt files).

[source](https://www.tecmint.com/35-practical-examples-of-linux-find-command/#:~:text=The%20find%20command%20is%20used,size%2C%20and%20other%20possible%20criteria.)

# -type
`-type` allows users to search for files based on their type

Example 1:

**COMMAND:**
```
find . -type d
```
**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218357849-ff226654-c145-4dac-8d99-969df6bcc4ec.png)

**Explanation**
In this command, the -type searches based on a certain type, and that type is directories because of the 'd' descriptor. As seen in the output, this command prints all the directories in the current working directory. In this case, it is the current working direcoty (the directory /written_2) because of the `.` in the command. This command is helpful for if someone would want to know all the subdirectories within a directory (if there are too many subdirectories that contain other subdirectories, it would be annoying to sort through all of them.  

[cite](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

Example 2:

**COMMAND:**
```
find travel_guides/berlitz1 -type f
```
**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218358585-0555c09f-f16b-4148-9a83-90ffea66a55f.png)
**Explanation**
In this command, the -type searches based on a certain type, and that type is a regular file because of the 'f' descriptor. As seen in the output, this command prints all the files in the directory travel_guides/berlitz1 based on the `travel_guides/berlitz1` in the argument. This command is helpful for finding all files in a specific directory, if a user would want to see what files a directory and its subdirectory might contain.   
[cite](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

# -size 
-size finds files based on its size

Example 1:

**COMMAND:**
```
find non-fiction/OUP -type f -size 10k
```
**OUTPUT**:
![image](https://user-images.githubusercontent.com/40574565/218360586-89db82a4-e0b7-4af9-a11f-33df2a8bc5de.png)
**Explanation**
In this command, find searches for files (specifically files based on the `-type f` in the command) in the directory non-fiction/OUP (specified in the command) with a size of exactly 10 kilobytes. This is because the `-size` has the descriptor `10k`, where k stands for kilobytes and 10 is the number of kilobytes. This command would be helpful for a user trying to find a file based on a certain size.  

[cite](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

Example 2:

**COMMAND:**
```
find . -type f -size +100k -size -200k
```
**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218360744-1ae18313-b9d0-427f-9a1a-84bdfb4e1300.png)
**Explanation**
In this command, find searches for files (based on the `-type f` in the command), in the current working directory (based on the `.` in the command) for files that are above 100 kilobytes and below 200 kilobytes. In the command, the -size specifies we are looking for a file of a certain size, and the +100k specifies the file is above 100 kilobytes, and the -200k specifies the file is below 200 kilobytes (k attribute means kilobytes). This command would be helpful for someone who wants to find a file of a certain size, e.g. to delete very large files or very small files. 

[cite](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

# -maxdepth
`-maxdepth` limits the depth of the search to a certain number 

Example 1:

**COMMAND:**
```
find . -maxdepth 1 -type d
```

**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218362675-30b5f94a-fb8c-4396-927b-0849bb2bcb4c.png)

**Explanation**

[cite](https://www.redhat.com/sysadmin/linux-find-command)

Example 2:

**COMMAND:**
```
find . -maxdepth 3 -type f
```
**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218363134-16aa7b30-b494-4079-85f8-ae6d3b3d9210.png)
**Explanation**

[cite](https://www.redhat.com/sysadmin/linux-find-command)
