# Ex.No:2(D) VARIABLE SCOPE AND CONSTRUCTOR

## QUESTION:

Write a program to access a static variable using both class name and object.

**For example:**

```text
48
```

Expected output:

```text
Accessing using class name: 48
Accessing using object: 48
```

## AIM:

To access a static variable using both the class name and an object in Java.

## ALGORITHM:

1. Start the program.
2. Declare a static integer variable `number`.
3. Read the value using `Scanner`.
4. Access the static variable using the class name.
5. Create an object of the class.
6. Access the same static variable using the object.
7. Display both values.
8. Stop the program.

## PROGRAM:

Program to access a static variable using class name and object.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class prog{
    public static int number;
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        number = scan.nextInt();
        System.out.println("Accessing using class name: "+prog.number);
        prog p = new prog();
        System.out.println("Accessing using object: "+p.number);
    }
}
```


## OUTPUT:

<img width="755" height="311" alt="output_static_variable" src="https://github.com/user-attachments/assets/ce7df8ae-1dda-437c-a783-5cbf48e86a5f" />


## RESULT:

Thus, the Java program to access a static variable using both class name and object was executed successfully.
