EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:
```
#include <stdio.h>
int main() {
    int num;
    printf("Enter a number (1-10): ");
    scanf("%d", &num);
    printf("The word for %d is: ", num);
    switch (num) {
        case 1:  printf("one"); break;
        case 2:  printf("two"); break;
        case 3:  printf("three"); break;
        case 4:  printf("four"); break;
        case 5:  printf("five"); break;
        case 6:  printf("six"); break;
        case 7:  printf("seven"); break;
        case 8:  printf("eight"); break;
        case 9:  printf("nine"); break;
        case 10: printf("ten"); break;
        default: printf("invalid input! Please enter number from 1 to 10.");
    }
    printf("\n");
    return 0;
}
```



Output:
```
Enter a number (1-10): 6
The word for 6 is: six


Enter a number (1-10): 12
The word for 12 is: invalid input! Please enter number from 1 to 10.

```




Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```
#include <stdio.h>
#include <string.h>
int main() {
    char input[100];
    int freq[10] = {0};
    printf("Enter a string of digits: ");
    scanf("%s", input);
    for (int i = 0; input[i] != '\0'; i++) {
        if (input[i] >= '0' && input[i] <= '3') {
            int digit = input[i] - '0';
            freq[digit]++;
        }
    }
    for (int i = 0; i < 10; i++) {
        printf("%d ", freq[i]);
    }
    printf("\n");
    return 0;
}
```


Output:


```
Enter a string of digits: 3
0 0 0 1 0 0 0 0 0 0 

Enter a string of digits: 15
0 1 0 0 0 0 0 0 0 0 
```


Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
void swap(char *x, char *y) {
    char temp = *x;
    *x = *y;
    *y = temp;
}
int compare(const void *a, const void *b) {
    return (*(char *)a - *(char *)b);
}
void reverse(char *str, int start, int end) {
    while (start < end) {
        swap(&str[start], &str[end]);
        start++;
        end--;
    }
}
int nextPermutation(char *str, int len) {
    int i = len - 2;
    while (i >= 0 && str[i] >= str[i + 1]) {
        i--;
    }
    if (i < 0) {
        return 0;
    }
    int j = len - 1;
    while (str[j] <= str[i]) {
        j--;
    }
    swap(&str[i], &str[j]);
    reverse(str, i + 1, len - 1);
    return 1;
}
int main() {
    char str[100];
    printf("Enter a string: ");
    scanf("%s", str);
    int len = strlen(str);
    qsort(str, len, sizeof(char), compare);
    do {
        printf("%s\n", str);
    } while (nextPermutation(str, len));
    return 0;
}
```


Output:

```
Enter a string: 21
12
21

Enter a string: 142
124
142
214
241
412
421
```



Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:
```
#include <stdio.h>
int main() {
    int n, i, j, num = 1;
    printf("Enter a value for N: ");
    scanf("%d", &n);
    for (i = 1; i <= n; i++) {
        for (j = 1; j <= i; j++) {
            printf("%d ", num);
            num++;
        }
        printf("\n");
    }
    return 0;
}
```



Output:


```
Enter a value for N: 12
1 
2 3 
4 5 6 
7 8 9 10 
11 12 13 14 15 
16 17 18 19 20 21 
22 23 24 25 26 27 28 
29 30 31 32 33 34 35 36 
37 38 39 40 41 42 43 44 45 
46 47 48 49 50 51 52 53 54 55 
56 57 58 59 60 61 62 63 64 65 66 
67 68 69 70 71 72 73 74 75 76 77 78 
```



Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:
```
#include <stdio.h>
int square() {
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}
int main() {
    int result;
    result = square(); 
    printf("The square of the number is: %d\n", result);
    return 0;
}
```



Output:
```
Enter a number: 99
The square of the number is: 9801

Enter a number: 1001
The square of the number is: 1002001
```



Result:
Thus, the program is verified successfully



























