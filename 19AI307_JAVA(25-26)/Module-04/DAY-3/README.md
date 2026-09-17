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
