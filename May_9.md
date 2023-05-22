# I choose find as my command 
#   - name: this is an option to find a specific name or name patern. This is useful because you could use it as a filter to find the file with the keyword you want. I find this option using ChatGPT. Correction: below is my prompt and how I modified with the response from chatGPT.

Prompt: find command line option
Response:
-name : This option is used to search for files/directories by name.
Example: find /path/to/directory -name "filename"

I changed from using exact string to find corresponding files to use * to find a larger scope of names and files.

example 1:
* correction:small description about what I am testing.
Use -name to provide a pattern to find the corresponding files.
This command is to find the file's name ending with .txt
```
 find . -name "*.txt"
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-13.1.txt
./chapter-13.2.txt
./chapter-13.3.txt
./chapter-3.txt
./chapter-2.txt
./chapter-1.txt
./chapter-5.txt
./chapter-6.txt
./chapter-7.txt
./chapter-9.txt
./chapter-8.txt
./preface.txt
./chapter-12.txt
./chapter-10.txt
./chapter-11.txt
```

* correction:small description about what I am testing.
example 2:
I am trying to find the file with 1 in it. adding a star in the front and behind would repsent n characters.
```
❯ find . -name "*1*.txt"
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-13.1.txt
./chapter-13.2.txt
./chapter-13.3.txt
./chapter-1.txt
./chapter-12.txt
./chapter-10.txt
./chapter-11.txt
```

#  - mtime <digit>:this is an option checking all the files that were modified with a period of time. It is important becuase we need to want some file that is just modified. I find this information from ChatGPT.
 Correction:</ br>
 my prompt is find command line option
ChatGPT's response:
 -mtime : This option is used to find files/directories modified within the last 'n' days.
Example: find /path/to/directory -mtime -7 (Files modified in the last 7 days)
 I change the number of the day, I want to check.
 correction:
 example 1: I change one file using vim. and I could check the modification with ls -l. After confirming my modification, I use mtime -7 chekcing the file that has been modified for past 7 days, I find the file.
```
❯ find . -mtime -7
❯ ls
chapter-1.txt    chapter-13.2.txt chapter-3.txt    chapter-9.txt
chapter-10.txt   chapter-13.3.txt chapter-5.txt    preface.txt
chapter-11.txt   chapter-13.4.txt chapter-6.txt
chapter-12.txt   chapter-13.5.txt chapter-7.txt
chapter-13.1.txt chapter-2.txt    chapter-8.txt
 
❯ vim chapter-1.txt
 
❯ ls -l
total 4432
-rwxr-xr-x@ 1 y  staff  118655  5  9 22:48 chapter-1.txt
-rwxr-xr-x@ 1 y  staff   47307  4 27 10:25 chapter-10.txt
-rwxr-xr-x@ 1 y  staff   71151  4 27 10:25 chapter-11.txt
-rwxr-xr-x@ 1 y  staff  127587  4 27 10:25 chapter-12.txt
-rwxr-xr-x@ 1 y  staff   89854  4 27 10:25 chapter-13.1.txt
-rwxr-xr-x@ 1 y  staff  110568  4 27 10:25 chapter-13.2.txt
-rwxr-xr-x@ 1 y  staff  150467  4 27 10:25 chapter-13.3.txt
-rwxr-xr-x@ 1 y  staff  265912  4 27 10:25 chapter-13.4.txt
-rwxr-xr-x@ 1 y  staff  290993  4 27 10:25 chapter-13.5.txt
-rwxr-xr-x@ 1 y  staff   79803  4 27 10:25 chapter-2.txt
-rwxr-xr-x@ 1 y  staff  264360  4 27 10:25 chapter-3.txt
-rwxr-xr-x@ 1 y  staff   99008  4 27 10:25 chapter-5.txt
-rwxr-xr-x@ 1 y  staff  149063  4 27 10:25 chapter-6.txt
-rwxr-xr-x@ 1 y  staff  128370  4 27 10:25 chapter-7.txt
-rwxr-xr-x@ 1 y  staff   84835  4 27 10:25 chapter-8.txt
-rwxr-xr-x@ 1 y  staff  149644  4 27 10:25 chapter-9.txt
-rwxr-xr-x@ 1 y  staff    9332  4 27 10:25 preface.txt
 
❯ find . -mtime -7
.
./chapter-1.txt
```

 example 2: I check the file that was modified in last 20 days, it shows all the file in this directory.
```
 ❯ find . -mtime -20
.
./chapter-13.4.txt
./chapter-13.5.txt
./chapter-13.1.txt
./chapter-13.2.txt
./chapter-13.3.txt
./chapter-3.txt
./chapter-2.txt
./chapter-1.txt
./chapter-5.txt
./chapter-6.txt
./chapter-7.txt
./chapter-9.txt
./chapter-8.txt
./preface.txt
./chapter-12.txt
./chapter-10.txt
./chapter-11.txt
```

#  - maxdepth: maxdepth limits the depth of the search to a specfic level. I can only search for two layers of subdirectory.This is important becuase, Sometime I just need to search through specific layers. I find this information from ChatGPT.
 Prompt: find command line option
 Response: The -maxdepth option is used with the find command in Unix/Linux systems to limit the depth of directories that the command will traverse.
 I changed the number of layers that I want to check.
 
 example 1 :I check the file only to the two sublayers of technical folder.
``` 
 ❯ find . -maxdepth 2 -type f
./DocSearchServer.java
./README.md
./lib/junit-4.13.2.jar
./lib/hamcrest-core-1.3.jar
./Server.java
./TestDocSearch.java
```
 Example 2: I checked the filed only to the one sublayers of techinical folder
```
 ./DocSearchServer.java
./README.md
./Server.java
./TestDocSearch.java
```
 
 #  -size <file size>: search the files based on the size. it is important that I could search based on file's szie. I find this information from ChatGPT.
 
 -size : This option is used to find files/directories of a specific size.
Example: find /path/to/directory -size +1M (Files larger than 1MB)
 
 Prompt: find command line option
 Response: -size : This option is used to find files/directories of a specific size.
Example: find /path/to/directory -size +1M (Files larger than 1MB)
 I change the size of the file.
 
Example 1: I checked the file size smaller than 1 kb. It shows the file that is smaller than 1kb.
```
 ❯ find . -size -1k  -type f
./README.md
./TestDocSearch.java
./technical/plos/pmed.0020191.txt
./technical/plos/pmed.0020226.txt
```
 Example 2:I checked the filed size larger than 1Mb.
 ``` 
 ❯ find . -size +1M  -type f
 ```
