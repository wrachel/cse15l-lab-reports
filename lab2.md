# Lab Report 2 - Servers and Bugs


## Part 1

## Part 2

Debugging the function averageWithoutLowest
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
