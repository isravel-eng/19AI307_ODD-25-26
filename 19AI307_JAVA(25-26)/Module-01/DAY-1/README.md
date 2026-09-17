# Ex.No:1(A) INTRODUCTION TO JAVA PROGRAMMING, DATA TYPES, VARIABLES AND OPERATORS

## QUESTION:

Lovely has just started learning Java and wants to understand how different output statements work.

The program should:

- Read Lovely's name, age, and favorite decimal number.
- Use `System.out.print()` to print the greeting.
- Use `System.out.println()` to print the age.
- Use `System.out.printf()` to print the favorite number with exactly 2 decimal places.

### Input Format

- First line: String — Lovely's name (no spaces)
- Second line: Integer — Lovely's age
- Third line: Float — Lovely's favorite decimal number

### Output Format

- `System.out.print()` → greeting message
- `System.out.println()` → age message
- `System.out.printf()` → favorite number formatted to 2 decimal places

### Example Input

```text
Lovely
20
3.14
```

### Example Output

```text
Hello, Lovely
You are 20 years old
Your favorite number is 3.14
```

## AIM:

To write a Java program that demonstrates the use of `print()`, `println()`, and `printf()` with user input.

## ALGORITHM:

1. Import the `Scanner` class.
2. Create a `Scanner` object to read input from the user.
3. Read the name using `next()`.
4. Read the age using `nextInt()`.
5. Read the favorite decimal number using `nextFloat()`.
6. Display the greeting using `System.out.print()`.
7. Display the age using `System.out.println()`.
8. Display the decimal number using `System.out.printf("%.2f", ...)`.
9. End the program.

## PROGRAM:

```java
Developed by : ISRAVEL Y
Register no  : 212225240054

import java.util.Scanner;

public class prog {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);

        String str = s.next();
        int a = s.nextInt();
        float f = s.nextFloat();

        System.out.print("Hello, " + str + "\n");
        System.out.println("You are " + a + " years old");
        System.out.printf("Your favorite number is %.2f", f);
    }
}
```

## Sourcecode.java:

```java
import java.util.Scanner;

public class prog {
    public static void main(String[] args) {
        Scanner s = new Scanner(System.in);

        String str = s.next();
        int a = s.nextInt();
        float f = s.nextFloat();

        System.out.print("Hello, " + str + "\n");
        System.out.println("You are " + a + " years old");
        System.out.printf("Your favorite number is %.2f", f);
    }
}
```

## OUTPUT:

<img width="747" height="348" alt="image" src="https://github.com/user-attachments/assets/c0b2fc0a-ac99-44a2-a9a1-5d4e3b78eee2" />


## RESULT:

Thus, the Java program was successfully executed using `System.out.print()`, `System.out.println()`, and `System.out.printf()` to display the required output in different printing styles.
