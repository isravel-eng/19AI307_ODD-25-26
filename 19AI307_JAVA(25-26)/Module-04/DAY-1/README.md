# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:

Write a Java program that reads two integers and divides the first integer by the second integer. Handle the case when division by zero occurs using exception handling and display an appropriate error message.

## AIM:

To implement exception handling in Java by handling an `ArithmeticException` caused by division by zero.

## ALGORITHM:

1. Start the program.
2. Import the `Scanner` class.
3. Read two integer values `a` and `b`.
4. Perform the division `a / b` inside a `try` block.
5. Display the result when the division is successful.
6. Catch `ArithmeticException` when the divisor is zero.
7. Display the error message for division by zero.
8. Stop the program.

## PROGRAM:

Program to demonstrate exception handling using `try` and `catch` in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class SafeDivision {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        
        int a = sc.nextInt();
        int b = sc.nextInt();

        try {
            int result = a / b;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero");
        }
    }
}
```

## OUTPUT:

<img width="697" height="395" alt="Screenshot 2026-09-17 183432" src="https://github.com/user-attachments/assets/9e5135d4-a889-4180-abb7-43c97e2343ab" />


## RESULT:

Thus, the Java program to perform safe division and handle division by zero using exception handling was executed successfully.
