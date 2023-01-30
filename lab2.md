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
The corrected code fixes the bug by accounting for the possibility that the lowest number repeats multiple times. In the for loop that iterates through the array, 
