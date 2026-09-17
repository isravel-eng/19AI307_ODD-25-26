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
