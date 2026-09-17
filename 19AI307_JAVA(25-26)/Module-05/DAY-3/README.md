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

## SAMPLE INPUT:

No keyboard input is required.

## SAMPLE OUTPUT:

```text
Successfully wrote to the file.
```

## OUTPUT:


## RESULT:

Thus, the Java program to write a string into `output.txt` using `FileWriter` was executed successfully.