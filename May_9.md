# I choose find as my command </br>
*  - name: this is an option to find a specific name or name patern. This is useful becuase you could use it as a filter to find the file with the keyword you want. I find this option using ChatGPT.</br>
example 1:
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

example 2:
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

* - mtime <digit>:this is an option checking all the files that were modified with a period of time. It is important becuase we need to want some file that is just modified. I find this information from ChatGPT.
 
 example 1: 
```
❯ find . -mtime -7
❯ ls
chapter-1.txt    chapter-13.2.txt chapter-3.txt    chapter-9.txt
chapter-10.txt   chapter-13.3.txt chapter-5.txt    preface.txt
chapter-11.txt   chapter-13.4.txt chapter-6.txt
chapter-12.txt   chapter-13.5.txt chapter-7.txt
chapter-13.1.txt chapter-2.txt    chapter-8.txt
```
 
 
![Image](remote.png)

# Remotely Connecting

![Image](terminal.png)
# Trying Some Commands
* ls is output the list of this current drictory
