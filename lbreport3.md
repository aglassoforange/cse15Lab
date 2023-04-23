

# Part 1

```
import java.io.IOException;
import java.net.URI;

  class Handler implements URLHandler {
    StringBuilder mess = new StringBuilder("");

    public String handleRequest(URI uri) throws RuntimeException {
        if (uri.getPath().equals("/")) {
            return "Out content is none";
        } else {
            System.out.println("Path: " + uri.getPath());
            if (uri.getPath().contains("/add-message")) {
                String[] parameters = uri.getQuery().split("=");
                if (parameters[0].equals("s")) {
                    mess.append(parameters[1]);
                    mess.append("\n");
                }
                return mess.toString();
            }
        }
        return "404 Not Found!";
    }
    
    public class StringServer{
        public static void main(String[] args) throws IOException{
            if(args.length == 0){
                System.out.println("missing port number");
                return;
            }
            int portNumber = Integer.parseInt(args[0]);
            Server.start(portNumber, new Handler());
            }
    }
}
```

![Image](vscode.png)

* Which methods in your code are called?
  main method, server.start(),hanldeRequst()

* What are the relevant arguments to those methods, and the values of any relevant fields of the class?
***
for main method it need a int input for port number.
for server.start, it needs portNumber and a new Handler.
for HandleRequest it needs a uri as a argument and Stringbuilder called mess.

* How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.
***
the value of stringbuilder is changed if the uri read from the browser has "/add-message?s" and it will add the string information after that.


![Image](remote.png)

# Part 2

*A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)

*An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)
*The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)
*The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

![Image](studentID.png)

* the student account can be check online
* the link of the id is https://sdacs.ucsd.edu/~icc/index.php and the screenshot is provided above.
* student account should be 9 digit code
* I am using McOs, thus I don't need to set up anything. I just use my search bar to find terminal
* Open teriminal and use ssh to connect
* ssh **********@ieng6.ucsd.edu

![Image](terminal.png)
# Trying Some Commands
* ls is output the list of this current drictory
* ls -l means to output more detailed info in this directory
* pwd  pwd command to find the path of your current working directory
* cp is copying the file to certain driectory

