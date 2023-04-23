

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

![Image](server1.png)
![Image](server2.png)
![Image](server.png)


* Which methods in your code are called?<br />
compile the code
```
%javac StringServer.java
%java StringServer <Port Number>
```
access the website
```
http://localhost:<Port Number>
```

main method, server.start(),hanldeRequst()
  

* What are the relevant arguments to those methods, and the values of any relevant fields of the class?<br />
for main method it need a int input for port number.
for server.start, it needs portNumber and a new Handler.
for HandleRequest it needs a uri as a argument and Stringbuilder called mess.

* How do the values of any relevant fields of the class change from this specific request? If no values got changed, explain why.<br />
the value of stringbuilder is changed if the uri read from the browser has "/add-message?s" and it will add the string information after that.



# Part 2
```
static int[] reversed(int[] arr) { int[] newArray = new int[arr.length]; for(int i = 0; i < arr.length; i += 1) { arr[i] = newArray[arr.length - i - 1]; } return arr; }
```
This is the code<br />


*A failure-inducing input for the buggy program, as a JUnit test and any associated code (write it as a code block in Markdown)<br />
```
 @Test 
	public void testReverseInPlace() {
    int[] input1 = { 3 };
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{ 3 }, input1);
	}
```

![Image](recode.png)


As shown above it couldn't return the right value for the corssponding Junit test.


*An input that doesn’t induce a failure, as a JUnit test and any associated code (write it as a code block in Markdown)<br />
```
	@Test 
	public void testReverseInPlace() {
   int[] input1 = { };
   assertArrayEquals(new int[]{ }, ArrayExamples.reversed(input1));
}
```
This input won't trigger a error.


*The symptom, as the output of running the tests (provide it as a screenshot of running JUnit with at least the two inputs above)<br />
![Image](recode.png)

*The bug, as the before-and-after code change required to fix it (as two code blocks in Markdown)

![Image](re.png)


Before:<br />
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];  
    return arr;
```


After:<br />

```
  static int[] reversed(int[] arr) {
    int[] b = new int[arr.length];
    int j = arr.length;
    for (int i = 0; i < arr.length; i++) {
        b[j - 1] = arr[i];
        j = j - 1;
    }
    return b;
```
Junit Test:<br />
![Image](testre.png)

The problem is that the value of arr[i] is being assigned tonewArray[arr.length - i - 1]. However, it is oppsite from what we want.

# Part 3 

From the past CSE15L class, I learned alot of things from how to build a simple server and interact with it from browser. I don't know that we could actually start the server by only using  Java excluding from the certian framework.

