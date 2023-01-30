# Lab Report 2 - Servers and Bugs


## Part 1
Code creating web server StringServer

```java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler{
    ArrayList<String> totalQueries = new ArrayList<String>(); 

     public String handleRequest(URI url) {
        //if search is add-message
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");

            totalQueries.add(parameters[1]);
            
            String concatQueries = "";
            for(String a : totalQueries){
                concatQueries += a + "\n";
            }
            return concatQueries;
        }
        else{
            return "Not found";
        }
        
    }
}

class StringServer{
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}

```
Two screenshots of method being used:
![image](https://user-images.githubusercontent.com/40574565/215366072-971fbd7d-dcd9-44f6-b4f8-0d3499c105fe.png)

* The class Handler() and method handleRequest(URI url) in the class Handler is called. 
* The relevant arguments to this method is the URI in the parameter, which gets the entire web address. Then the if loop checks if the URL path contains /add-message. The parameters split the query by the "=". `parameters[1]` becomes grapes, and the code adds that to an arraylist. The arraylist concats all the values to the String concatQueries and returns this variable, which gets displayed on the web page. Another relevant argument is the args[] in the main method which gets the port 4000.
* The relevant fields of the class change depending on what users input. For example, the URI depends on what the user inputs. Here, I used the input /add-message?s=grapes, which displays grapes on the page. If the user does not input  `add-message` it will return a 404 error or put something else besides grapes, it would display something differet.

![image](https://user-images.githubusercontent.com/40574565/215366311-f14a0814-047c-407c-988b-fd5b7dc2c866.png)
* The class Handler() and method handleRequest(URI url) in the class Handler is called. 
* The relevant arguments to this method is the URI in the parameter, which gets the entire web address. Then the if loop checks if the URL path contains /add-message. The parameters split the query by the "=". `parameters[1]` becomes hello, and the code adds that to the arraylist totalQueries, which already contains grapes. The arraylist concats all the values to the String concatQueries and returns this variable, which gets displayed on the web page. Then, the webpage displays both grapes and hello. 
* The relevant fields of the class change depending on what users input. For example, the URI depends on what the user inputs. Here, I used the input /add-message?s=hello, which displays hello on the page, in addition to grapes. 

![image](https://user-images.githubusercontent.com/40574565/215366441-7da30de1-1d35-4f92-94ed-28dc2575790e.png)
In this image:
* The class Handler() and method handleRequest(URI url) in the class Handler is called. 
* The relevant arguments to this method is the URI in the parameter, which gets the entire web address. Then the if loop checks if the URL path contains /add-message. Since it doesn't a "Not found" message is displayed. 
* The relevant fields of the class change depending on what users input. For example, the URI depends on what the user inputs. Here, I did not use /add-message, which changes what would be displayed. 

## Part 2

Debugging the function averageWithoutLowest

Below is the code for averageWithoutLowest **with bugs** 
```java
 static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    for(double num: arr) {
      if(num < lowest) { lowest = num; }
    }
    double sum = 0;
    for(double num: arr) {
      if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - 1);
  }
```

Failure-inducing input: {1, 1, 1, 10, 20, 3} 
```java
@Test
  public void testAverageBugged(){
    double[] input1 = {1, 1, 1, 10, 20, 3};
    assertEquals(11.0, ArrayExamples.averageWithoutLowest(input1), 0.1);
  }
```
JUnit test for failure-inducing input:
![image](https://user-images.githubusercontent.com/40574565/215363587-1d99e95b-6d64-4fd4-b518-2508ece98e6a.png)
This is a failure-inducing input because the lowest number (1) repeats multiple times in the input array. But, when calculating the average, the method only does `arr.length - 1`, and does not consider the times that the lowest number may repeat. That's why the actual value was 6.6 instead of 11.0, since the method calculated the average as (10+20+3)/(6-1) = 6.6.

Input that doesn't induce a failure: {1, 2, 3, 4}
```java
  @Test 
  public void testAverageCorrect(){
    double[] input1 = {1, 2, 3, 4};
    assertEquals(3.0, ArrayExamples.averageWithoutLowest(input1), 0.1);
  }
```
JUnit test for input that **does not** induce a failure
![image](https://user-images.githubusercontent.com/40574565/215363736-54f968e3-edda-4cc4-bd84-a71e84de296d.png)
This input does not induce a failure because the lowest number only occurs once, so it does not matter that the method does not consider the possibility of the lowest number repeating. The expected outcome is 3.0, and the actual outcome is also 3.0.

**Corrected code:**
```java
static double averageWithoutLowest(double[] arr) {
    if(arr.length < 2) { return 0.0; }
    double lowest = arr[0];
    int numLowest = 0;

    for(double num: arr) {
      if(num < lowest) { 
        lowest = num;
      }
    }
    double sum = 0;
    for(double num: arr) {
      if(num == lowest){
        numLowest++;
      }
      else if(num != lowest) { sum += num; }
    }
    return sum / (arr.length - numLowest);
  }
```
The corrected code fixes the bug by accounting for the possibility that the lowest number repeats multiple times. In the second for loop that iterates through the array, if the number is equal to the lowest, it increments the variable "numLowest." Returning `sum / (arr.length - numLowest)` accounts for the fact that the lowest number may appear multiple times. 

After fixing the bug, both JUnit tests have no failures:
![image](https://user-images.githubusercontent.com/40574565/215364080-37fc4bc9-62cb-407c-be60-caeec71817fa.png)

## Part 3
