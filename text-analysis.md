# Text Analysis

## Goal
Your assignment is to write a C++ program to read in a file of English text, and determine the number of occurrences of each letter/character on the file. Additionally you will count how many times there are certain words (conjunctions). This assignment will allow you to practice working with arrays and reinforce your proficiency working with files.

## Program Output
The text for Our Father, The King James Bible and A Tale of Two Cities was copied into files “ourfather.txt”, “kj-bible.txt” and “2city10.txt”. My solution to this assignment was run using these files.  The following screenshot shows what your program should output when Our Father file is specified.

As you can see it has counted the number occurrences of each of the characters found on file. Note that it shows the character counted, its ASCII code, its count and its relative percentage. What’s more the program counted the occurrences of the conjunctions FOR, AND, NOR, BUT, OR, YET, and SO, showing also the relative percentage for each of these words.

## Implementation using arrays
This lab assignment gives you the opportunity to practice using arrays.  As you read through the characters in the text, you will use one array (a “size_t” array of 256 elements) to count the number of each character, and you will use one set of parallel array to count the number of occurrences of the conjunctions.

## Functions you need to write
You are to write the following five functions for your main program to call:

Function | Description
-------- | ------------
`CountCharacters`	| **Counts how many characters there are**. Takes a file, the array of `size_t` that represents the count of each character of the ASCII table, the size of the array (although the size is always 256). Returns the number of characters read, unless there was an error reading in which case the function returns -1.
`CountWords` | **Counts how many conjunctions there are**. Takes a file, a set of parallel arrays (2), one that represents the count of each of the conjunctions, and the array of strings that represents the actual conjunctions, and the size of these arrays. Remember, since it is a set of parallel arrays they are supposed to be of the same size. The function returns the number of conjunctions found in the file, unless there was an error reading in which case the function returns -1.
`ToUpper` | **Converts a string to capital letters**. Takes a string as parameter and returns a string with all capitalized letters. This function will be used to compare with the article words that are capitalized.
`WriteCharacterCount` | **Outputs the Character count table**. Outputs the formatted character count table, notice from the sample output that it only outputs the characters found, for instance in that file there was no ‘+’, so there is no ‘+’ in the table. The table has the following columns heading: *Char*, *Code*, *Count*, *%*. When you find a character with ASCII code 10, instead of printing that “invisible” character, print `LF`; and if the character ASCII code is 13 print `CR`. Hint: `cout << static_cast<char>(65) << endl;` Outputs the letter A.
`WriteWordCount` | **Outputs the Conjunction count table**. Outputs the formatted conjunctions table. Be careful not to print `nan`, so, validate in the case of a zero count.

### Note
You may write additional functions, but you must write the aforementioned functions.

### Sample Output
```
Filename: ourfather.txt
 Char Code   Count       %
--------------------------
        32      55   18.97
    ,   44       4    1.38
    .   46       3    1.03
    ;   59       3    1.03
    A   65       1    0.34
    F   70       1    0.34
    G   71       1    0.34
    H   72       2    0.69
    K   75       1    0.34
    O   79       1    0.34
    T   84       3    1.03
    W   87       1    0.34
    a   97      20    6.90
    b   98       4    1.38
    c   99       1    0.34
    d  100      10    3.45
    e  101      27    9.31
    f  102       3    1.03
    g  103       4    1.38
    h  104      10    3.45
    i  105      16    5.52
    l  108       8    2.76
    m  109       6    2.07
    n  110      15    5.17
    o  111      16    5.52
    p  112       3    1.03
    r  114      13    4.48
    s  115      18    6.21
    t  116      15    5.17
    u  117       9    3.10
    v  118       7    2.41
    w  119       4    1.38
    y  121       5    1.72

    Word   Count       %
------------------------
     FOR       0    0.00
     AND       2   66.67
     NOR       0    0.00
     BUT       1   33.33
      OR       0    0.00
     YET       0    0.00
      SO       0    0.00
```

## Main Program
The main program first prompts the user to enter a file name.  You will open that file for input.  If the file is not successfully opened, you will print an informative error message and exit the main program.

Next you will initialize all count arrays to zero.

You will then begin reading through the file character by character using your `CountCharacters` function. Afterwards you will read the file again, using your `CountWords` function, from the beginning, word by word this time, to count the conjunctions words, remember to change each word that you read to capital letters.

After you finish reading through the file, you will of course close the file.  Finally you will call your `WriteCharacterCount` and `WriteWordCount` functions to output the tables.


## Error Handling

Other than checking the file was opened successfully or any issues reading the file, you should not have to include any other error handling. Your program should not crash and should never give a NaN output.

## Program Style

Please refer to the Lab 1 assignment document for appropriate style.
Here are some additional style rule:
When you design your functions:
- Make sure that all object parameters are passed by reference.  In other words, if you are passing a string object or a stream object, pass by reference.
- If you don’t intend for your function to modify an object or array parameter, place const keyword before the parameter.  The compiler will then make sure you do not accidentally modify that parameter.   In this lab many, but not all, of the object and array parameters of the functions described above should be declared const.

## Guidance specific to this lab

1. Define a `const int` variable equal to 256, and use that instead of 256 everywhere in the code.  Our style guide for `const` variables is that their name should be descriptive and in all capital letters.
1. For the parallel arrays, you should not specify the size when you define the array of specific words, use a constant array to store the conjunction words.  Let C++ count it for you based on the list of words you initialize it with.  Then use `sizeof(<name of words array>)/sizeof(<name of words array>[0])` when you specify the size of the count array.
1. When counting letters remember that `letters_count_array['A']` is the same as to say `letters_count_array[65]` since `65` is the ASCII code of letter `A`. That is why you need an array of 256 elements to count each of the letters.

## Submitting your code

Your solution should be contained within a single C++ file, and it must be named `textanalysis.cpp`.

Before submitting:
1. From CLion build your program.
1. The executable file will be placed in a directory called `cmake-build-debug` inside your project directory. Suppose that your project is on `C:\CLionProjects\` and that your project name is `text-analysis-joe`, then your source file `textanalysis.cpp` will be in `C:\CLionProjects\text-analysis-joe\` and your executable will be in `C:\CLionProjects\text-analysis-joe\cmake-build-debug\`
1. Open a Command Prompt window
1. Move to **your** `cmake-build-debug` directory of your Text Analysis project using `cd`. For example, when you open your command prompt you will be in a directory `C:\Users\Joe` then move using `cd C:\CLionProjects\text-analysis-joe`. **Notice that this applies to this example you will need to move to your appropriate directory**.
1. The test files *“ourfather.txt”*, *“kj-bible.txt”* and *“2city10.txt”* should be in the project folder, since you must have cloned this repository there.
1. First test:
   1. Run the executable using ourfather.txt: `text_analysis.exe`
   1. Your program is going to show the message `Filename: ` type: `..\ourfather.txt`
   1. Your program will show an output like the one shown in [Sample Output](#sample-output)
1. Check the output of testing each of the files, redirecting the output to compare with provided expected outputs:
   1. Run the executable using ourfather.txt: `text_analysis.exe > ..\myoutput1.txt` you will not see anything on the screen, type: `..\ourfather.txt` and then hit ENTER.
   1. Run the command `fc ..\ourfather-output.txt ..\myoutput1.txt` you should see no output or a message saying that there are no differences.
   1. Run the executable using `kj-bible.txt`: `text_analysis.exe > ..\myoutput2.txt` you will not see anything on the screen, type: `..\kj-bible.txt` and then hit ENTER.
   1. Run the command `fc ..\kj-bible-output.txt ..\myoutput2.txt` you should see no output or a message saying that there are no differences.
   1. Run the executable using `2city10.txt`: `text_analysis.exe > ..\myoutput3.txt` you will not see anything on the screen, type: `..\2city10.txt` and then hit ENTER.
   1. Run the command `fc ..\dickens-output.txt ..\myoutput3.txt` you should see no output or a message saying that there are no differences.
   1. Notice that in your project directory, there will be three new files: myoutput1.txt, myoutput2.txt and myoutput3, leave those files there.
1. When you have passed these three tests you can make your final push.

### Note for Mac Users
Mac users are going to change every backslash `\` to forward slash `/` to access parent directories.

## Grading
Correctness is essential.  Make sure your solution builds as described above and correctly handles all three test files.  We will test on other input file(s) as well.

Even if your solution operates correctly, points will be taken off for:
- Not following the design described above
- Not adhering to style guidelines described above
- Using techniques not presented in class
- Programming error not caught by other testing
- Not following good programming practices

## Academic Integrity
This programming assignment is to be done on an individual basis. At the same time, it is understood that learning from your peers is valid and you are encouraged to talk among yourselves about programming in general and current assignments in particular.  Keep in mind, however, that each individual student must do the work in order to learn.  Hence, the following guidelines are established:
- Feel free to discuss any and all programming assignments but do not allow other students to look at or copy your code. Do not give any student an electronic or printed copy of any program you write for this class.
- Gaining the ability to properly analyze common programming errors is an important experience. Do not deprive a fellow student of his/her opportunity to practice problem solving: control the urge to show them what to do by writing the code for them.
- If you’ve given the assignment a fair effort and still need help, see the instructor or a lab assistant.
- **If there is any evidence that a program or other written assignment was copied from another student, neither student will receive any credit for it. This rule will be enforced.**
- Protect yourself: Handle throw-away program listings carefully, keep your repository private.

Refer to the ECS Department Policy on Academic Integrity that is included in the class syllabus.

## Grading Rubric Summary
The following aspects are going to be consider during grading. Make sure you comply with all of them.
-	The program compiles (there will be no partial credit for programs that do not compile)
-	Provides the correct output for Test 1, Test 2, Test 3 and Test 4 (The first three were given to you, the fourth was not)
-	Catches errors gracefully, the program does not crash on incorrect input
-	The program outputs the information in the specified format
-	The program counts the characters correctly
-	The program counts the conjunctions correctly
-	The program follows the good programming practices discussed in class
- The program follows the coding conventions discussed in class
-	The assignment follows all the instructions
-	In general the program does not crash
