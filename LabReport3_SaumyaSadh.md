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

This we will be exploring the `grep` command in detail. `grep` is a command tool that, given a string and a file, identifies and displays all lines within that file that contain the specified string.

### Command-line Option 1: `grep -w`

**Examples of using it on files and directories**

**Example 1**

input 
```
grep -w "search" ./technical/file1.txt
```
output 
```
search: This is a sample line to search for a specific word.
```
**Description:** 

This command searches for the whole word "search" in the file `file1.txt`. The `-w` option ensures that only the exact word "search" is matched, excluding instances where "search" is part of a larger word.


**Example 2**
input
```
grep -w "four" technical/911report/chapter-1.txt

```
output
```

```

**Description:** (what it is doing and why it is useful) 




### Command-line Option 2: `grep -i`

**Examples of using it on files and directories:**

**Example 1**
```

```

**Description:** (what it is doing and why it is useful) 


**Example 2**
```

```

**Description:** (what it is doing and why it is useful) 




### Command-line Option 3: `grep -v`

**Examples of using it on files and directories:**

**Example 1**

```

```
**Description:** (what it is doing and why it is useful) 

**Example 2**

```

```

**Description:** (what it is doing and why it is useful) 



### Command-line Option 4: `grep -r`

**Examples of using it on files and directories:**

**Example 1**
```

```

**Description:** (what it is doing and why it is useful) 


**Example 2**
```

```

**Description:** (what it is doing and why it is useful) 













