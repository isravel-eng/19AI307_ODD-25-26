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
