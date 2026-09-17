# Ex.No:4(A) EXCEPTION HANDLING

## QUESTION:

Write a Java program that reads two integers and divides the first integer by the second integer. Handle the case when division by zero occurs using exception handling and display an appropriate error message.

## AIM:

To implement exception handling in Java by handling an `ArithmeticException` caused by division by zero.

## ALGORITHM:

1. Start the program.
2. Import the `Scanner` class.
3. Read two integer values `a` and `b`.
4. Perform the division `a / b` inside a `try` block.
5. Display the result when the division is successful.
6. Catch `ArithmeticException` when the divisor is zero.
7. Display the error message for division by zero.
8. Stop the program.

## PROGRAM:

Program to demonstrate exception handling using `try` and `catch` in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class SafeDivision {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        
        int a = sc.nextInt();
        int b = sc.nextInt();

        try {
            int result = a / b;
            System.out.println("Result: " + result);
        } catch (ArithmeticException e) {
            System.out.println("Error: Division by zero");
        }
    }
}
```

## OUTPUT:

<img width="697" height="395" alt="Screenshot 2026-09-17 183432" src="https://github.com/user-attachments/assets/9e5135d4-a889-4180-abb7-43c97e2343ab" />


## RESULT:

Thus, the Java program to perform safe division and handle division by zero using exception handling was executed successfully.

# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM

## QUESTION:

Implement the Observer pattern for a smart-city Air Quality Index (AQI) sensor network. Create a `SensorNetwork` as the subject and `SmartController` classes as observers. The controllers are `GreenZoneController`, `AlertZoneController`, and `DangerZoneController`, each reacting only to its corresponding AQI range.

- `GreenZoneController`: AQI < 100
- `AlertZoneController`: AQI between 100 and 200
- `DangerZoneController`: AQI > 200

When the sensor network receives an AQI reading, notify the registered observers and allow only the relevant controller to take action.

## AIM:

To implement the Observer design pattern in Java by allowing AQI controllers to receive and process sensor notifications according to their assigned ranges.

## ALGORITHM:

1. Start the program.
2. Define an `Observer` interface with the `check()` method.
3. Create `GreenZoneController`, `AlertZoneController`, and `DangerZoneController` classes implementing the interface.
4. Create the `SensorNetwork` subject with a list of observers.
5. Register the three controllers with the sensor network.
6. Read the number of AQI readings.
7. Read each sensor ID and AQI value.
8. Display the sensor reading and notify all registered observers.
9. Each controller checks the AQI range and reacts only when its condition is satisfied.
10. Stop the program.

## PROGRAM:

Program to implement the Observer pattern for an AQI monitoring system using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.*;

interface Observer {
    void check(int aqi, String sensorId);
}

class GreenZoneController implements Observer {
    public void check(int aqi, String sId){
        if (aqi<100){
            System.out.println("[GreenZoneController]: AQI is good at Sensor "+sId+". No action needed.");
        }
    }
}

class AlertZoneController implements Observer {
     public void check (int aqi, String sId){
         if (aqi>=100 && aqi<=200){
             System.out.println("[AlertZoneController]: Moderate AQI at Sensor "+sId+". Send public health alert.");
         }
     }
}

class DangerZoneController implements Observer {
     public void check (int aqi, String sId){
         if(aqi>200){
             System.out.println("[DangerZoneController]: Critical AQI at Sensor "+sId+"! Trigger lockdown protocol.");
         }
     }
}

class SensorNetwork {
    private List<Observer> observers = new ArrayList<>();
    
    public void register(Observer observer){
        observers.add(observer);
    }
    
    public void receiveData(String id, int aqi){
        System.out.println("Sensor "+id+" reports AQI: "+aqi);
        for(Observer o:observers){
            o.check(aqi,id);
        }
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        SensorNetwork network = new SensorNetwork();

        network.register(new GreenZoneController());
        network.register(new AlertZoneController());
        network.register(new DangerZoneController());

        int n = sc.nextInt(); sc.nextLine();
        for (int i = 0; i < n; i++) {
            String[] parts = sc.nextLine().split(" ");
            String id = parts[0];
            int aqi = Integer.parseInt(parts[1]);
            network.receiveData(id, aqi);
        }
    }
}
```


## OUTPUT:

<img width="856" height="385" alt="Screenshot 2026-09-17 183644" src="https://github.com/user-attachments/assets/3af47997-b969-4f3a-92b3-5787565369e4" />


## RESULT:

Thus, the Java program to implement the Observer pattern for an AQI sensor network was executed successfully.

# Ex.No:4(C)  COMPOSITION IN JAVA

## QUESTION:

Implement a Java program in which a `Library` contains multiple `Book` objects. Each `Book` is created inside the `Library`, demonstrating composition. Read the number of books and their title and author, create the books through the `Library`, and display all books.

## AIM:

To implement composition in Java by creating and managing `Book` objects inside a `Library` object.

## ALGORITHM:

1. Start the program.
2. Create a `Book` class with private `title` and `author` fields.
3. Create a constructor to initialize a book's title and author.
4. Create a `Library` class containing a list of `Book` objects.
5. Add a method in `Library` to create and store books.
6. Read the number of books and their details.
7. Create each `Book` through the `Library` object.
8. Display all books stored in the library.
9. Stop the program.

## PROGRAM:

Program to demonstrate composition between `Library` and `Book` classes using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.*;

public class CompositionExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        Library library = new Library();

        int n = sc.nextInt();
        sc.nextLine();

        for (int i = 0; i < n; i++) {
            String title = sc.nextLine();
            String author = sc.nextLine();
            library.addBook(title, author);
        }

        library.showBooks();
        sc.close();
    }
}

class Book {
    private String title;
    private String author;

    public Book(String title, String author) {
        this.title = title;
        this.author = author;
    }

    public String getDetails() {
        return title + " by " + author;
    }
}

class Library {
    List<Book> books = new ArrayList<>();
    public void addBook(String title, String author) {
        books.add(new Book(title,author));
    }

    public void showBooks() {
        System.out.println("Books in Library:");
        for(Book book : books){
            System.out.println("- "+book.getDetails());
        }
    }
}
```

## OUTPUT:

<img width="866" height="631" alt="Screenshot 2026-09-17 183800" src="https://github.com/user-attachments/assets/9c66d993-bac3-4104-945b-4a1c82300158" />


## RESULT:

Thus, the Java program to demonstrate composition by creating `Book` objects inside a `Library` was executed successfully.

# Ex.No:4(D) DESIGN PATTERN -- ABSTRACT FACTORY

## QUESTION:

You are creating a cross-platform UI tool using the Abstract Factory pattern. Implement factories to create `Button` and `Checkbox` objects for `dark` and `light` themes. Let the user choose the theme, generate the corresponding UI components, and display their types.

## AIM:

To implement the Abstract Factory design pattern in Java by creating related `Button` and `Checkbox` objects for different themes.

## ALGORITHM:

1. Start the program.
2. Define `Button` and `Checkbox` product interfaces.
3. Create light and dark implementations of both products.
4. Define the `UIFactory` interface with factory methods for creating the products.
5. Create `LightUIFactory` and `DarkUIFactory` classes implementing `UIFactory`.
6. Read the selected theme from the user.
7. Create the appropriate factory based on the selected theme.
8. Use the factory to create a button and checkbox.
9. Render both UI components.
10. Stop the program.

## PROGRAM:

Program to implement the Abstract Factory design pattern for light and dark UI themes using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

interface Button{
    void render();
}

interface Checkbox {
    void render();
}

class LightButton implements Button{
    @Override 
    public void render(){
        System.out.println("Light Button created");
    }
}

class DarkButton implements Button{
    @Override 
    public void render(){
        System.out.println("Dark Button created");
    }
}

class LightCheckbox implements Checkbox{
    @Override 
    public void render(){
        System.out.println("Light Checkbox created");
    }
}

class DarkCheckbox implements Checkbox{
    @Override 
    public void render(){
        System.out.println("Dark Checkbox created");
    }
}

interface UIFactory{
    Button createButton();
    Checkbox createCheckbox();
}

class DarkUIFactory implements UIFactory{
    @Override 
    public Button createButton(){
        return new DarkButton();
    }
    
    @Override 
    public Checkbox createCheckbox(){
        return new DarkCheckbox();
    }
}

class LightUIFactory implements UIFactory{
    @Override 
    public Button createButton(){
        return new LightButton();
    }
    
    @Override 
    public Checkbox createCheckbox(){
        return new LightCheckbox();
    }
}

public class prog{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String input = in.next();
        Button b; Checkbox c; UIFactory factory;
        if (input.equalsIgnoreCase("light")){
            factory = new LightUIFactory();
            b = factory.createButton();
            c = factory.createCheckbox();
            b.render();
            c.render();
        }
        else if (input.equalsIgnoreCase("dark")){
            factory = new DarkUIFactory();
            b = factory.createButton();
            c = factory.createCheckbox();
            b.render();
            c.render();
        }
        else{
            System.out.println("Invalid theme");
        }
    }
}
```


## OUTPUT:

<img width="671" height="375" alt="Screenshot 2026-09-17 185352" src="https://github.com/user-attachments/assets/5c3b4f41-50f4-4f07-978c-235ebe7b8df0" />


## RESULT:

Thus, the Java program to implement the Abstract Factory design pattern for light and dark UI components was executed successfully.

# Ex.No:4(D) DESIGN PATTERN  ---- BEHAVIOUR PATTERN

## QUESTION:

Design a Java product management system using the Model-View-Controller (MVC) approach. Create a `Product` model to store the product name, price, and code. Create a view to display the product details and a controller to update the product price and refresh the view automatically.

## AIM:

To implement separation of model, view, and controller responsibilities in a Java product management system and demonstrate automatic view refresh after updating the model.

## ALGORITHM:

1. Start the program.
2. Create the `Product` model with name, price, and code fields.
3. Provide getters and a setter for the product price.
4. Create the `ProductView` class to display product information.
5. Create the `ProductController` class to connect the model and view.
6. Read the product name, price, code, and new price.
7. Create the product controller with the initial product details.
8. Call `updateView()` to display the initial details.
9. Call `updatePrice()` to modify the price and refresh the view.
10. Stop the program.

## PROGRAM:

Program to demonstrate model, view, and controller separation in a Java product management system.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class ProductManagementSystem {

    // ===== Model =====
    static class Product {
        private String name;
        private double price;
        private String code;

        // TODO: Constructor to initialize name, price, code
        Product(String name,double price, String code){
            this.name = name;
            this.price = price;
            this.code = code;
        }

        // TODO: Getter for name
        public String getName(){
            return name;
        }

        // TODO: Getter for price
        public double getPrice(){
            return price;
        }

        // TODO: Getter for code
        public String getCode(){
            return code;
        }

        // TODO: Setter for price
        public void setPrice(double price){
            this.price = price;
        }
    }

    // ===== View =====
    static class ProductView {
        public void displayProduct(String name, double price, String code) {
            System.out.println("--- Product Details ---");
            System.out.println("Name : " + name);
            System.out.println("Price: " + price);
            System.out.println("Code : " + code);
        }
    }

    // ===== Controller =====
    static class ProductController {
        private Product product;
        private ProductView view;

        // TODO: Constructor to initialize product and view
        ProductController(String name,double price, String code){
            product = new Product(name,price,code);
            view = new ProductView();
        }

        // TODO: Method updateView() → calls view.displayProduct()
        public void updateView(){
            view.displayProduct(product.getName(),product.getPrice(),product.getCode());
        }

        // TODO: Method updatePrice(double) → sets new price and refreshes view
        public void updatePrice(double price){
            product.setPrice(price);
            view.displayProduct(product.getName(),product.getPrice(),product.getCode());
        }
    }

    // ===== Main Method =====
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        // TODO: Take input - name, price, code, newPrice

        // TODO: Create Product, View, and Controller objects
        ProductController pc = new ProductController(sc.next(),sc.nextDouble(),sc.next());
        
        // TODO: Call controller.updateView()
        pc.updateView();
        
        // TODO: Call controller.updatePrice(newPrice)
        pc.updatePrice(sc.nextDouble());
        
        sc.close();
    }
}
```

## OUTPUT:

<img width="653" height="402" alt="Screenshot 2026-09-17 185453" src="https://github.com/user-attachments/assets/5cf442af-a680-4b53-a7e3-6e8b616eb291" />


## RESULT:

Thus, the Java program to implement model, view, and controller separation and update the product price with automatic view refresh was executed successfully.

