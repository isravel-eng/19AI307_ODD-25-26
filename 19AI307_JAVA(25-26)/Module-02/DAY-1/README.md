# Ex.No:2(A) CLASSES AND OBJECTS

## QUESTION:

Create a class `Car` with attributes `brand`, `model`, `year`. Create 2 objects and print their details.

**For example:**

```text
Car 1: Toyota Innova 2022
Car 2: Hyundai i20 2021
```

## AIM:

To create a Java class with attributes, create two objects, assign values, and display their details.

## ALGORITHM:

1. Start the program.
2. Create a class `Car` with `brand`, `model`, and `year`.
3. Create two `Car` objects.
4. Assign the required values to both objects.
5. Display the details of both cars.
6. Stop the program.

## PROGRAM:

Program to create a class and objects in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
public class prog {
    public static void main(String[] args) {
        Car car1 = new Car();
        car1.brand = "Toyota";
        car1.model = "Innova";
        car1.year = 2022;

        Car car2 = new Car();
        car2.brand = "Hyundai";
        car2.model = "i20";
        car2.year = 2021;

        System.out.println("Car 1: " + car1.brand + " " + car1.model + " " + car1.year);
        System.out.println("Car 2: " + car2.brand + " " + car2.model + " " + car2.year);
    }
}

class Car{
    String brand,model;
    int year;
}
```



## OUTPUT:

<img width="677" height="277" alt="output_class_objects" src="https://github.com/user-attachments/assets/b114a3f4-aee7-44f3-8315-3aafdfa46600" />


## RESULT:

Thus, the Java program to create a class, create two objects, and display their details was executed successfully.
