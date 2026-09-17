# Ex.No:1(B) CONDITIONAL STATEMENT

## QUESTION:

A pirate ship has a code lock that only opens if:

- The input code is even:
  - If it is less than 100, display **"Weak Code"**.
  - If it is between 100 and 999, display **"Strong Code"**.
- If the code is odd, display **"Access Denied"**.
- Codes outside the range 0–999 are also denied access by the program.

### Input Format

- First line: An integer representing the code.

### Output Format

- Display **"Weak Code"** for an even code less than 100.
- Display **"Strong Code"** for an even code between 100 and 999.
- Display **"Access Denied"** for an odd code or an even code outside the specified range.

### Sample Input

```text
42
```

### Sample Output

```text
Weak Code
```

## AIM:

To write a Java program using conditional statements to check whether a given code is even and classify it as a **Weak Code**, **Strong Code**, or **Access Denied** based on its value.

## ALGORITHM:

1. Start the program.
2. Import the `Scanner` class from `java.util` package.
3. Create a `Scanner` object to read input from the user.
4. Read the integer code.
5. Check whether the code is even using `code % 2 == 0`.
6. If the code is even, check whether it is less than 100.
7. If the code is less than 100, display **"Weak Code"**.
8. Otherwise, check whether the code is between 100 and 999.
9. If it is between 100 and 999, display **"Strong Code"**.
10. Otherwise, display **"Access Denied"**.
11. If the code is odd, display **"Access Denied"**.
12. Close the `Scanner` and stop the program.

## PROGRAM:

```java
/*
Program to implement a conditional statement using Java
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

        int code = sc.nextInt();

        if (code % 2 == 0) {

            if (code < 100) {
                System.out.println("Weak Code");
            }
            else if (code >= 100 && code <= 999) {
                System.out.println("Strong Code");
            }
            else{
            System.out.println("Access Denied");
            }

        } else {
            System.out.println("Access Denied");
        }

        sc.close();
    }
}
```

## OUTPUT:

<img width="432" height="307" alt="image" src="https://github.com/user-attachments/assets/c511897b-80c4-4773-a283-a0091443c67d" />


## RESULT:

Thus, the Java program was successfully implemented using **if-else conditional statements** to check the code and display **"Weak Code"**, **"Strong Code"**, or **"Access Denied"** according to the given conditions.
