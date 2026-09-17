# Ex.No:3(F) WRAPPER CLASS

## QUESTION:

Write a Java program to demonstrate the use of a Wrapper Class by converting a primitive integer value into an `Integer` object using autoboxing and converting the `Integer` object back into a primitive integer using unboxing. Display both values.

## AIM:

To demonstrate the use of the `Integer` wrapper class and the concepts of autoboxing and unboxing in Java.

## ALGORITHM :

1. Start the program.
2. Read an integer value using `Scanner`.
3. Convert the primitive `int` value into an `Integer` object using autoboxing.
4. Convert the `Integer` object back into an `int` using unboxing.
5. Display the original primitive value and the unboxed value.
6. Stop the program.

## PROGRAM:

Program to demonstrate Wrapper Class using autoboxing and unboxing in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class prog{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        int number = scan.nextInt();
        Integer obj = number;
        int value = obj;
        System.out.println("Primitive value: " + number);
        System.out.println("Wrapper object: " + obj);
        System.out.println("Unboxed value: " + value);
    }
}
```

## SAMPLE INPUT:

```text
25
```

## SAMPLE OUTPUT:

```text
Primitive value: 25
Wrapper object: 25
Unboxed value: 25
```

## RESULT:

Thus, the Java program to demonstrate the Integer Wrapper Class using autoboxing and unboxing was executed successfully.
