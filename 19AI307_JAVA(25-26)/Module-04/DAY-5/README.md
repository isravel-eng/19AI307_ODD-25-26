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
