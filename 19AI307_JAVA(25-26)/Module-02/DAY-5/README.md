# Ex.No:2(E) ACCESS MODIFIERS

## QUESTION:

Create a class `SpeedLimit` with a final method `displayLimit()` that prints `"Max Speed: 80 km/h"`. Try to override it in a subclass. Show that overriding a final method is not allowed.

## AIM:

To demonstrate that a `final` method cannot be overridden in a subclass.

## ALGORITHM:

1. Start the program.
2. Create the `SpeedLimit` class.
3. Declare `displayLimit()` as a `final` method.
4. Display the maximum speed inside the method.
5. Create the `HighwaySpeed` subclass.
6. Do not override the final method because Java does not allow it.
7. Create a `HighwaySpeed` object through a `SpeedLimit` reference.
8. Call `displayLimit()`.
9. Stop the program.

## PROGRAM:

Program to demonstrate the use of a final method in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
class SpeedLimit {
    final void displayLimit() {
         System.out.println("Max Speed: 80 km/h");
    }
}

class HighwaySpeed extends SpeedLimit {

}

public class prog {
    public static void main(String[] args){
        SpeedLimit s = new HighwaySpeed();
        s.displayLimit();
    }
}
```

## SAMPLE INPUT:

No keyboard input is required.

## OUTPUT:

<img width="560" height="257" alt="output_final_method" src="https://github.com/user-attachments/assets/80b7882f-5f53-4a2a-aba9-88be88cfcc3b" />


## RESULT:

Thus, the Java program demonstrating that a final method cannot be overridden was executed successfully.
