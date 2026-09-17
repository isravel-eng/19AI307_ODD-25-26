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
