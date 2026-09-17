# Ex.No:5(B) SERIALIZATION AND DESERIALIZATION

## QUESTION:

Write a Java program to serialize a collection of `Student` objects stored in an `ArrayList` into a file named `students.dat`. Then deserialize the collection from the file and display the student details.

**For example:**

```text
2
101
Alice
89.5
102
Bob
92.0
```

Expected output:

```text
Students serialized successfully into: students.dat
Students deserialized successfully from: students.dat

Deserialized Students:
Student{id=101, name='Alice', marks=89.5}
Student{id=102, name='Bob', marks=92.0}
```

## AIM:

To demonstrate serialization and deserialization of a collection of Java objects using `ObjectOutputStream` and `ObjectInputStream`.

## ALGORITHM:

1. Start the program.
2. Create a `Student` class that implements `Serializable`.
3. Read the number of students and their details.
4. Store the students in an `ArrayList`.
5. Serialize the list into `students.dat` using `ObjectOutputStream`.
6. Deserialize the list using `ObjectInputStream`.
7. Display the deserialized student details.
8. Handle input/output and class-related exceptions.
9. Stop the program.

## PROGRAM:

Program to demonstrate serialization and deserialization of an `ArrayList<Student>` using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.io.*;
import java.util.*;

// Student class must implement Serializable
class Student implements Serializable {
    private static final long serialVersionUID = 1L;

    private int id;
    private String name;
    private double marks;

    public Student(int id, String name, double marks) {
        this.id = id;
        this.name = name;
        this.marks = marks;
    }

    @Override
    public String toString() {
        return "Student{id=" + id + ", name='" + name + "', marks=" + marks + "}";
    }
}

public class StudentSerializationUserInput {

    // Serialize list of students
    public static void serializeStudents(List<Student> students, String fileName) {
        try (ObjectOutputStream oos = new ObjectOutputStream(new FileOutputStream(fileName))) {
            oos.writeObject(students);
            System.out.println("Students serialized successfully into: " + fileName);
        } catch (IOException e) {
            System.out.println("Error during serialization: " + e.getMessage());
        }
    }

    // Deserialize list of students
    @SuppressWarnings("unchecked")
    public static List<Student> deserializeStudents(String fileName) {
        List<Student> students = null;
        try (ObjectInputStream ois = new ObjectInputStream(new FileInputStream(fileName))) {
            students = (List<Student>) ois.readObject();
            System.out.println("Students deserialized successfully from: " + fileName);
        } catch (IOException | ClassNotFoundException e) {
            System.out.println("Error during deserialization: " + e.getMessage());
        }
        return students;
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        List<Student> students = new ArrayList<>();

        int n = in.nextInt();
        in.nextLine(); // consume newline

    
        for(int i=0;i<n;i++){
            students.add(new Student(in.nextInt(),in.next(),in.nextDouble()));
        }
        
        StudentSerializationUserInput.serializeStudents(students,"students.dat");
        List<Student> deserializedStudents = StudentSerializationUserInput.deserializeStudents("students.dat");

        
        // Display deserialized data
        if (deserializedStudents != null) {
            System.out.println("\nDeserialized Students:");
            for (Student s : deserializedStudents) {
                System.out.println(s);
            }
        }

        in.close();
    }
}
```

## SAMPLE INPUT:

```text
2
101
Alice
89.5
102
Bob
92.0
```

## SAMPLE OUTPUT:

```text
Students serialized successfully into: students.dat
Students deserialized successfully from: students.dat

Deserialized Students:
Student{id=101, name='Alice', marks=89.5}
Student{id=102, name='Bob', marks=92.0}
```

## OUTPUT:


## RESULT:

Thus, the Java program to serialize and deserialize a collection of `Student` objects was executed successfully.