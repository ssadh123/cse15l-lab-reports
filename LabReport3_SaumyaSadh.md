# Part 1 - Bugs 

### 1) jUnit Test that results in failure due to buggy code 
&nbsp;

```
int[] input2 = {1,2,3};
ArrayExamples.reverseInPlace(input2);
assertArrayEquals(new int[]{3, 2, 1} input2);

```


### 2) Input that does not induce failure 
&nbsp;
```
int[] input3 = {1,2,3};
ArrayExamples.reverseInPlace(input3);
assertArrayEquals(new int[]{1,2,3} input3);
```
### 3) The symptom as output of running the test
&nbsp;
![Image](symptom.png);



### 4) Before - and - after changes 
&nbsp;

**Before Fix**

```
 static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }

```

**After Fix**
```
static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length / 2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }


```
### Brief Discription of the fix: 
&nbsp;
The original issue in the `reverseInPlace` method resulted from overwriting elements directly without preserving their 
values, leading to data loss and incorrect results, especially after the midpoint of the array. The fix corrects this by:

&nbsp;

**Limiting the loop to half the array length** to ensure each element pair is swapped only once, preventing elements from
being swapped back to their original positions.

&nbsp;

**Introducing a temporary variable (`temp`)** to hold the value of the current element during the swap, preserving data 
integrity and ensuring a correct swap.

&nbsp;

**Implementing correct swapping logic** that ensures each element and its counterpart are swapped correctly, allowing the method to accurately reverse the array for any length, thereby maintaining the integrity of the data throughout the process.
&nbsp;
# Part 2 - Researching Commands






