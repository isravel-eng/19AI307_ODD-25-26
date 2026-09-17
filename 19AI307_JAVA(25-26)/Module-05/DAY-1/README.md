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
