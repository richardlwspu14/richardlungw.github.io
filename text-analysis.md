# Text Analysis

## Goal
Your assignment is to write a C++ program to read in a file of English text, and determine the number of occurrences of each letter/character on the file. Additionally you will count how many times there are certain words (conjunctions). This assignment will allow you to practice working with arrays and reinforce your proficiency working with files.

## Program Output
The text for Our Father, The King James Bible and A Tale of Two Cities was copied into files “ourfather.txt”, “kj-bible.txt” and “2city10.txt”. My solution to this assignment was run using these files.  The following screenshot shows what your program should output when Our Father file is specified.

As you can see it has counted the number occurrences of each of the characters found on file. Note that it shows the character counted, its ASCII code, its count and its relative percentage. What’s more the program counted the occurrences of the conjunctions FOR, AND, NOR, BUT, OR, YET, and SO, showing also the relative percentage for each of these words.

## Implementation using arrays
This lab assignment gives you the opportunity to practice using arrays.  As you read through the characters in the text, you will use one array (a “size_t” array of 256 elements) to count the number of each character, and you will use one set of parallel array to count the number of occurrences of the conjunctions.

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
