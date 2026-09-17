# Ex.No:1(E) STRINGS AND MATH FUNCTION

## QUESTION:

**Write a Java program to calculate the power of a given number.**

### Sample Input

```text
3
2
```

### Sample Output

```text
3.0 raised to the power of 2.0 is: 9.0
```

## AIM:

To write a Java program to calculate the power of a given number using the `Math.pow()` function.

## ALGORITHM:

1. Start the program.
2. Import the `Scanner` class from the `java.util` package.
3. Create a `Scanner` object to read the input.
4. Read the base number as a `double`.
5. Read the power as a `double`.
6. Use `Math.pow(number, power)` to calculate the result.
7. Store the result in a `double` variable.
8. Display the number, power, and calculated result.
9. Stop the program.

## PROGRAM:

```java
/*
Program to implement a Strings and Math Function using Java
Developed by: ISRAVEL Y
RegisterNumber: 212225240054
*/
```

## SOURCE CODE:

```java
import java.util.Scanner;

public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        double number = sc.nextDouble();
        double power = sc.nextDouble();

        double result = Math.pow(number, power);

        System.out.println(number + " raised to the power of " 
                           + power + " is: " + result);
    }
}
```

## OUTPUT:

<img width="975" height="336" alt="image" src="https://github.com/user-attachments/assets/eca95cd4-ef92-4eac-9323-f8ca0d40c418" />


## RESULT:

Thus, the Java program was successfully implemented using the **Math.pow()** function to calculate the power of a given number.

