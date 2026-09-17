# Ex.No:1(D) ARRAYS

## QUESTION:

**Write a Java Program to Find the Average of Array Elements.**

### Sample Input

```text
5
10
20
30
40
50
```

### Sample Output

```text
The average of elements is 30.00
```

## AIM:

To write a Java program to store elements in an array and calculate the average of all the array elements.

## ALGORITHM:

1. Start the program.
2. Import the `Scanner` class from the `java.util` package.
3. Create a `Scanner` object to read the input.
4. Read the number of array elements `n`.
5. Create an integer array of size `n`.
6. Initialize the sum to `0`.
7. Use a `for` loop to read each array element.
8. Add each element to the sum.
9. Calculate the average using `sum / n`.
10. Display the average with two decimal places using `printf()`.
11. Stop the program.

## PROGRAM:

```java
/*
Program to implement a Array concept using Java
Developed by: ISRAVEL Y
RegisterNumber: 212225240054
*/
```

## SOURCE CODE:

```java
import java.util.Scanner;

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int n = sc.nextInt();
        int[] arr = new int[n];

        float sum = 0;

        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
            sum += arr[i];
        }

        System.out.printf("The average of elements is %.2f",(sum/n));
    }
}
```

## OUTPUT:

<img width="857" height="546" alt="image" src="https://github.com/user-attachments/assets/cb96fbc0-0587-4bb2-bd79-33dc5e04ceae" />


## RESULT:

Thus, the Java program was successfully implemented using an **array and for loop** to calculate and display the average of the array elements.

