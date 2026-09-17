# Ex.No:1(C) LOOPING STATEMENT

## QUESTION:

Reversing a number means rearranging its digits in the opposite order. For example:

- The reverse of `1234` is `4321`.
- The reverse of `9870` is `789` because leading zeros in the reversed number are not shown.

Write a Java program that takes an integer input from the user and reverses its digits using a **while loop**.

- Repeatedly extract the last digit using the modulus operator (`%`).
- Build the reversed number using the extracted digit.
- Continue the loop until the number becomes `0`.
- Finally, display the reversed number.

### Sample Input

```text
5600
```

### Sample Output

```text
Reversed number: 65
```

## AIM:

To write a Java program to reverse the digits of a given integer using a **while loop**, modulus operator (`%`), and integer division.

## ALGORITHM:

1. Start the program.
2. Import the `Scanner` class from the `java.util` package.
3. Create a `Scanner` object to read the input.
4. Read the integer number.
5. Initialize `reverse` to `0`.
6. Repeat the following steps while `num > 0`:
   - Find the last digit using `num % 10`.
   - Add the digit to the reversed number using `reverse = reverse * 10 + num % 10`.
   - Remove the last digit using `num /= 10`.
7. Display the reversed number.
8. Stop the program.

## PROGRAM:

```java
/*
Program to implement a Looping Statement using Java
Developed by: ISRAVEL Y
RegisterNumber: 212225240054
*/
```

## SOURCE CODE:

```java
import java.util.Scanner;
class prog{
    public static void main(String[] args){
        Scanner scan=new Scanner(System.in);
        int num=scan.nextInt();
        int reverse=0;
        while(num>0){
            reverse = (reverse*10) + (num%10);
            num /=10;
        }
        System.out.printf("Reversed number: %d",reverse);
    }
}
```

## OUTPUT:

<img width="673" height="348" alt="image" src="https://github.com/user-attachments/assets/94d4aa49-6f5f-420c-a197-ed072c92ab82" />


## RESULT:

Thus, the Java program was successfully implemented using a **while loop** to reverse the digits of a given integer and display the reversed number.

