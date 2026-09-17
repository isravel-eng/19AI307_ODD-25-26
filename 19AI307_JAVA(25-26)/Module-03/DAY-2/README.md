
# Ex.No:3(b) POLYMORPHISM

## QUESTION:

Write a Java program that calculates the area of different shapes using method overloading. Create a class `AreaCalculator` with:

- `area(int side)` for square
- `area(int length, int breadth)` for rectangle
- `area(double radius)` for circle

**For example:**

```text
4
5 6
3.0
```

```text
Area of square: 16
Area of rectangle: 30
Area of circle: 28.274333882308138
```

## AIM:

To implement compile-time polymorphism using method overloading for calculating the areas of different shapes.

## ALGORITHM:

1. Start the program.
2. Create a class `AreaCalculate`.
3. Define three overloaded `area()` methods for square, rectangle, and circle.
4. Read the side of the square.
5. Read the length and breadth of the rectangle.
6. Read the radius of the circle.
7. Call the appropriate overloaded method for each shape.
8. Display the calculated areas.
9. Stop the program.

## PROGRAM:

Program to implement polymorphism using method overloading in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class prog{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        AreaCalculate calc = new AreaCalculate();
        int s = scan.nextInt();
        System.out.println("Area of square: "+calc.area(s));
        int l = scan.nextInt(); int b = scan.nextInt();
        System.out.println("Area of rectangle: "+calc.area(l,b));
        double r = scan.nextDouble();
        System.out.println("Area of circle: "+calc.area(r));
        
    }
}

class AreaCalculate{
    int area(int side){
        return side * side;
    }
    int area(int length, int breadth){
        return length*breadth;
    }
    double area(double radius){
        return Math.PI*radius*radius;
    }
}
```

## SAMPLE INPUT:

```text
4
5 6
3.0
```

## OUTPUT:

<img width="885" height="473" alt="Screenshot 2026-09-17 172347" src="https://github.com/user-attachments/assets/742e1706-c533-4b0a-b39f-6942ac713035" />

## RESULT:

Thus, the Java program to calculate the area of different shapes using method overloading was executed successfully.
