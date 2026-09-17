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

# Ex.No:2(C) ACCESS SPECIFIERS

## QUESTION:

Write a Java program to create a class called `Smartphone` with private instance variables `brand`, `model`, and `storageCapacity`. Provide public getter and setter methods to access and modify these variables. Add a method called `increaseStorage()` that takes an integer value and increases the `storageCapacity` by that value.

## AIM:

To implement encapsulation using private instance variables, public getter and setter methods, and a method to increase storage capacity.

## ALGORITHM:

1. Start the program.
2. Create the `Smartphone` class.
3. Declare `brand`, `model`, and `storageCapacity` as private variables.
4. Create public getter and setter methods.
5. Create `increaseStorage(int value)` to increase storage capacity.
6. Read brand, model, and storage values.
7. Display the updated smartphone details.
8. Stop the program.

## PROGRAM:

Program to demonstrate encapsulation using getter, setter, and update methods.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

class Smartphone {
    private String brand;
    private String model;
    private int storageCapacity;


    public String getBrand() {
        return brand;
    }

    public String getModel() {
        return model;
    }

    public int getStorageCapacity() {
        return storageCapacity;
    }


    public void setBrand(String brand) {
        this.brand = brand;
    }

    public void setModel(String model) {
        this.model = model;
    }

    public void setStorageCapacity(int storageCapacity) {
        this.storageCapacity = storageCapacity;
    }


    public void increaseStorage(int value) {
        if (value > 0) {
            this.storageCapacity += value;
        }
    }


    public void display() {
        System.out.println("Brand: " + brand);
        System.out.println("Model: " + model);
        System.out.println("Updated Storage Capacity: " + storageCapacity + " GB");
        System.out.println("------------------------------");
    }
}

public class prog{
    public static void main(String[] args){
        Smartphone p = new Smartphone();
        Scanner scan = new Scanner(System.in);
        p.setBrand(scan.nextLine());
        p.setModel(scan.nextLine());
        p.setStorageCapacity(scan.nextInt()+scan.nextInt());
        p.display();
    }
}
```

## OUTPUT:

<img width="992" height="480" alt="output_encapsulation" src="https://github.com/user-attachments/assets/3fb637f6-fef8-4458-aec4-a01033e7a248" />


## RESULT:

Thus, the Java program to implement encapsulation using private variables and public methods was executed successfully.

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
