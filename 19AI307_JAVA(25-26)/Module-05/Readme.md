# Ex.No:5(A) INPUTSTREAMREADER

## QUESTION:

Write a Java program to demonstrate chaining of streams using `BufferedReader` on top of `InputStreamReader` on top of `System.in`. Read the user's name and age and display the details.

**For example:**

```text
Ram
25
```

Expected output:

```text
--- User Details ---
Name: Ram
Age: 25
```

## AIM:

To demonstrate stream chaining in Java using `System.in`, `InputStreamReader`, and `BufferedReader` for reading input.

## ALGORITHM:

1. Start the program.
2. Create an `InputStreamReader` using `System.in`.
3. Create a `BufferedReader` using the `InputStreamReader`.
4. Read the user name using `readLine()`.
5. Read the age and convert it into an integer.
6. Display the user details.
7. Close the `BufferedReader`.
8. Stop the program.

## PROGRAM:

Program to demonstrate chaining of input streams using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class ChainingStreamsExample {
    public static void main(String[] args) throws IOException{
        // Chaining: System.in -> InputStreamReader -> BufferedReader
        InputStreamReader isr = new InputStreamReader(System.in);
        BufferedReader br = new BufferedReader(isr);
        String name = br.readLine();
        int age = Integer.parseInt(br.readLine());
        System.out.println("--- User Details ---\nName: "+name+"\nAge: "+age);
        br.close();
    }
}
```


## OUTPUT:

<img width="656" height="560" alt="Screenshot 2026-09-17 200708" src="https://github.com/user-attachments/assets/44e16bcc-aaaf-4492-bb7c-745d754472e1" />


## RESULT:

Thus, the Java program to demonstrate chaining of `BufferedReader`, `InputStreamReader`, and `System.in` was executed successfully.


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

## OUTPUT:

<img width="858" height="540" alt="Screenshot 2026-09-17 201022" src="https://github.com/user-attachments/assets/a6cb657b-6d02-42c4-aebd-135cb0bd8019" />


## RESULT:

Thus, the Java program to serialize and deserialize a collection of `Student` objects was executed successfully.


# Ex.No:5(C)  FILE HANDLING USING JAVA

## QUESTION:

Write a Java program to write a string to a text file named `output.txt` using `FileWriter`. Display a confirmation message after successfully writing the data.

**For example:**

```text
Successfully wrote to the file.
```

## AIM:

To demonstrate file handling in Java by writing text into a file using `FileWriter`.

## ALGORITHM:

1. Start the program.
2. Import the required I/O package.
3. Create a string containing the text to be written.
4. Create a `FileWriter` for `output.txt`.
5. Write the string into the file.
6. Close the `FileWriter`.
7. Display the success message.
8. Stop the program.

## PROGRAM:

Program to write a string into a text file using Java file handling.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.io.*;
public class prog{
    public static void main(String[] args) throws IOException{
        String text = "I am Isravel";
        FileWriter fw  = new FileWriter("output.txt");
        fw.write(text);
        fw.close();
        System.out.println("Successfully wrote to the file.");
    }
}
```


## OUTPUT:

<img width="797" height="231" alt="image" src="https://github.com/user-attachments/assets/108ddf31-579c-4fce-882b-776c006e9b31" />


## RESULT:

Thus, the Java program to write a string into `output.txt` using `FileWriter` was executed successfully.


# Ex.No:5(D) THREAD PRIORITY

## QUESTION:

Write a Java program to determine the priority and name of the current thread. Read the thread name from the user, set its priority to `5`, and display the priority, thread name, and thread information.

**For example:**

```text
NewThread
```

Expected output:

```text
Priority of Thread: 5
Name of Thread: NewThread
Thread[NewThread,5,main]
```

## AIM:

To demonstrate how to set and retrieve the name and priority of the current thread in Java.

## ALGORITHM:

1. Start the program.
2. Create a `Scanner` object to read the thread name.
3. Get the current thread using `Thread.currentThread()`.
4. Set the thread name using the input value.
5. Set the thread priority to `5`.
6. Retrieve and display the thread priority.
7. Retrieve and display the thread name and thread information.
8. Stop the program.

## PROGRAM:

Program to demonstrate thread name and priority using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import  java.util.Scanner;

public class prog{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        Thread t = Thread.currentThread();
        t.setName(in.nextLine());
        t.setPriority(5);
        System.out.print("Priority of Thread: "+t.getPriority()+"\nName of Thread: "+t.getName()+"\n"+t);
    }
}
```

## OUTPUT:

<img width="717" height="273" alt="image" src="https://github.com/user-attachments/assets/8802a152-29c6-47a4-92ac-357494319094" />


## RESULT:

Thus, the Java program to determine and display the name and priority of the current thread was executed successfully.


# Ex.No:5(E) MULTITHREADING -SYNCHRONIZATION

## QUESTION:

Write a Java program to read `N` integers from the user and use a fixed thread pool of size `3` to process each number. Each task must multiply its input by `2` and return the result. Display the results in the same order as the input.

**For example:**

```text
3
5
10
15
```

Expected output:

```text
Result: 10
Result: 20
Result: 30
```

## AIM:

To demonstrate multithreading in Java using a fixed thread pool and process multiple tasks while preserving the order of their results.

## ALGORITHM:

1. Start the program.
2. Create a `Scanner` to read the input.
3. Read the number of tasks `T`.
4. Create a fixed thread pool with `3` threads.
5. Submit one task for each input number.
6. Each task multiplies its number by `2` and returns the result.
7. Store the returned `Future` objects in input order.
8. Retrieve and display each result in the same order.
9. Shut down the thread pool.
10. Stop the program.

## PROGRAM:

Program to demonstrate a fixed thread pool for processing multiple tasks concurrently in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.*;
import java.util.concurrent.*;

public class prog {
    public static void main(String[] args) throws Exception {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();

        ExecutorService pool = Executors.newFixedThreadPool(3);
        List<Future<Integer>> results = new ArrayList<>();

        for (int i = 0; i < t; i++) {
            int n = sc.nextInt();
            results.add(pool.submit(() -> n * 2));
        }

        for (Future<Integer> result : results) {
            System.out.println("Result: " + result.get());
        }

        pool.shutdown();
        sc.close();
    }
}
```

## OUTPUT:

<img width="490" height="541" alt="Screenshot 2026-09-17 201547" src="https://github.com/user-attachments/assets/babdafa3-61de-442e-a01f-865a6c7edfc6" />


## RESULT:

Thus, the Java program to process multiple tasks using a fixed thread pool of size 3 and display the results in input order was executed successfully.

