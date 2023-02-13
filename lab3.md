# Lab 3

### Exploring 'find'

In this lab, I will be exploring the different command-line options for the command `find`

A little information about find:
find searches the directory tree starting from the working directory (or directory specified), and can be used to find files based on certain conditions (e.g. file name, content, etc.)
[source](https://man7.org/linux/man-pages/man1/find.1.html) [source](https://www.tecmint.com/35-practical-examples-of-linux-find-command/#:~:text=The%20find%20command%20is%20used,size%2C%20and%20other%20possible%20criteria.)

### -name

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

### -type
`-type` allows users to search for files based on their type
**COMMAND:**
```
find . -type d
```
**OUTPUT:**
![image](https://user-images.githubusercontent.com/40574565/218357849-ff226654-c145-4dac-8d99-969df6bcc4ec.png)

**Explanation**
In this command, the -type searches for commands based on a certain type, and that type is directories because of the 'd' descriptor. As seen in the output, this command prints all the directories in the current working directory. In this case, it is the current working direcoty (the directory /written_2) because of the `.` in the command. This command is helpful for if someone would want to know all the subdirectories within a directory (if there are too many subdirectories that contain other subdirectories, it would be annoying to sort through all of them.  

[cite](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)
