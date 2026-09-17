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

## SAMPLE INPUT:

```text
dark
```

## SAMPLE OUTPUT:

```text
Dark Button created
Dark Checkbox created
```

## OUTPUT:


## RESULT:

Thus, the Java program to implement the Abstract Factory design pattern for light and dark UI components was executed successfully.