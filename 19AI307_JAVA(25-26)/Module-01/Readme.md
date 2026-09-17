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
