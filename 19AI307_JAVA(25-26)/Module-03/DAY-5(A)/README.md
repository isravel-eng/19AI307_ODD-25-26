# Ex.No:3(E) INNER CLASS

## QUESTION:

Write a Java program to create an enum `Season` with values `WINTER`, `SPRING`, `SUMMER`, and `FALL`. Use a switch statement to display a custom message based on the current season.

**For example:**

Input:

```text
winter
```

Output:

```text
It's cold outside. Stay warm!
```

Other outputs:

```text
fall
Leaves are falling. Autumn is beautiful!
```

```text
spring
Flowers are blooming. Enjoy the fresh air!
```

```text
summer
It's sunny and hot. Time for the beach!
```

## AIM:

To create an enum in Java and use a switch statement to display a message based on the selected season.

## ALGORITHM:

1. Start the program.
2. Create the `Season` enum with `WINTER`, `SPRING`, `SUMMER`, and `FALL`.
3. Read the season as a string.
4. Convert the input to uppercase.
5. Convert the string into the corresponding enum value using `valueOf()`.
6. Use a switch statement to select the appropriate message.
7. Display the message for the selected season.
8. Handle invalid input using `IllegalArgumentException`.
9. Stop the program.

## PROGRAM:

Program to implement an enum and switch statement using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

enum Season {
    WINTER, SPRING, SUMMER, FALL;
}

public class prog{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        String season = in.next().toUpperCase();
        
        try{
            Season s = Season.valueOf(season);
            switch (s){
                case WINTER:
                    System.out.println("It's cold outside. Stay warm!");
                    break;
                case SPRING:
                    System.out.println("Flowers are blooming. Enjoy the fresh air!");
                    break;
                case SUMMER:
                    System.out.println("It's sunny and hot. Time for the beach!");
                    break;
                case FALL:
                    System.out.println("Leaves are falling. Autumn is beautiful!");
                    break;
            }
        }
        catch(IllegalArgumentException e){
            System.out.println("-------");
        }
    }
}
```

## SAMPLE INPUT:

```text
winter
```

## SAMPLE OUTPUT:

```text
It's cold outside. Stay warm!
```

## OUTPUT:


## RESULT:

Thus, the Java program to create an enum and display season-specific messages using a switch statement was executed successfully.
