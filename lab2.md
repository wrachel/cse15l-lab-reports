# Lab Report 2 - Servers and Bugs


## Part 1

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
This is a failure-inducing input because the lowest number (1) repeats multiple times in the input array. But, when calculating the average, the method only does the 'arr.length - 1'

Input that doesn't induce a failure: {1, 2, 3, 4}
```java
  @Test 
  public void testAverageCorrect(){
    double[] input1 = {1, 2, 3, 4};
    assertEquals(3.0, ArrayExamples.averageWithoutLowest(input1), 0.1);
  }
```

Corrected code:
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
