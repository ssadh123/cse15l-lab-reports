## Step 1
Clone this repository using the command line: https://github.com/ucsd-cse15l-f23/skill_demo3_data. 
Use the https url to clone. Make sure that the name of the directory is skill_demo3_data.

```
git clone  https://github.com/ucsd-cse15l-f23/skill_demo3_data

cd skill_demo3_data

```
## Step 2
Find the path to the `.java` file with the most lines among all files in the `submissions/` directory. 
Store the path to that file (either absolute or relative from the skill_demo3_data directory) in the file `biggest.txt`.

**input** 
```
find submissions -name "*.java" | xargs wc -l | sort -n

or

find submissions -name "*.java" -exec wc -l {} + > out.txt
sort out. txt 

```
**output** : on the last line - copy the last line into file `biggest.txt`
```
34 submissions/student5/Sorter.java 

```

##Step 3
Find all the lines in all the `.java` files that contain the string `Collections.sort`.
Store the content of these lines in a file called `sorts.txt`.

**input**

```
grep -r "Collections.sort" --include=*.java 

```

**output**: copy paste the output you get into 'sorts.txt` 

```
submissions/student1/Sorter.java:    Collections.sort(a); // sort using a library function to save time
submissions/student6/Sorter.java:    Collections.sort(a);
submissions/student4/pa3-code/Sorter.java:    Collections.sort(nums);
```

## Step 4

The remaining steps are concerned with `grade.sh`. The condition in the if statement that checks for compile errors is incomplete. 
Fix this condition so that it evaluates to `true` if there was a compile error. 
Rerun the script with the updated behavior (some submissions should now have results.txt files that report compile errors.

1. Go into `grade.sh`
   
**wrong code**
```
if false
  then
    echo "$submission_dir: Compile error" > result.txt    
    cd $original_dir
    continue
  else


```
**corrected code**

```
if [ $? -ne 0 ]
```

**re-run using**

```
bash grade.sh

```

## Part 5

Add code to the end of the script so that the concatenation of all `result.txt` files for all students whose programs successfully ran are stored in `run-results.txt` (in the same directory as the script already stores compile-errors.txt). Rerun the script with the updated behavior (there should now be a file called run-results.txt with passed/failed information for each submission).

**Add this code to the script** : 
```
cat $all_results | grep "Test" > run-results.txt 

```

**re-run using**

```
bash grade.sh

```


## Possible Part 6

Be able to **search for a speacific file** and how many times it appeads in director recursivly 

```
find submissions -name "*.java"
```

**Appeared 6 times in this case**

## Possible part 7 

Re-direct Standard eroor, and changing the script to handle standard error 

Try to do something on these lines 

```
java > stdout.txt 2> stderr.txt

```






