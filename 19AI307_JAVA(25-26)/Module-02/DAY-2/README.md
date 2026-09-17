# Ex.No:2(B) METHOD AND PASSING VALUE

## QUESTION:

Write a method `void modifyValue(int num)` that tries to modify the passed value and print `"Inside method: "+num`.

Show in `main()` that the original value does not change.

After calling `modifyValue(int num)` method in `main`, print the `"Outside method: "+num`.

**For example:**

```text
10
```

Expected output:

```text
Inside method: 20
Outside method: 10
```

## AIM:

To demonstrate that modifying a primitive `int` parameter inside a method does not change the original variable in `main()`.

## ALGORITHM:

1. Start the program.
2. Create the method `modifyValue(int num)`.
3. Add 10 to the parameter inside the method.
4. Print the modified value inside the method.
5. Read the original value in `main()`.
6. Call `modifyValue(num)`.
7. Print the original value outside the method.
8. Stop the program.

## PROGRAM:

Program to demonstrate parameter passing using an integer value.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.*;

public class prog{
    public void modifyValue(int num){
        num +=10;
        System.out.println("Inside method: "+num);
    }
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        prog p = new prog();
        int num = scan.nextInt();
        p.modifyValue(num);
        System.out.println("Outside method: "+num);
    }
}
```


## OUTPUT:

<img width="607" height="272" alt="output_method" src="https://github.com/user-attachments/assets/c341b6de-6bb2-4d1b-b2c2-ddf9331f9f9e" />


## RESULT:

Thus, the Java program demonstrating modification of a primitive value inside a method was executed successfully, and the original value remained unchanged.
