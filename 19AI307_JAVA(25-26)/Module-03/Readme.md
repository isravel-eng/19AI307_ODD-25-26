# Ex.No:3(A) INHERITANCE AND AGGREGATION

## QUESTION:

Create a Super class `Person` with fields `name` and `age`. Create a subclass `Student` that inherits from `Person` and adds a field `marks` (integer). Implement a method in `Student` called `calculateGrade()` which returns the grade based on the marks:

- Marks ≥ 90: Grade A
- Marks ≥ 75 and < 90: Grade B
- Marks ≥ 50 and < 75: Grade C
- Marks < 50: Grade F

## AIM:

To implement inheritance by creating a superclass `Person` and a subclass `Student`, and to calculate a grade based on marks.

## ALGORITHM:

1. Start the program.
2. Create a superclass `Person` with `name` and `age` fields.
3. Create a subclass `Student` that extends `Person` and adds the `mark` field.
4. Define the `calculateGrade()` method in `Student`.
5. Read the student's name, age, and marks.
6. Calculate the grade using the given mark ranges.
7. Display the student details and grade.
8. Stop the program.

## PROGRAM:

Program to implement inheritance and aggregation concepts using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

class Person{
    String name;
    int age;
}

class Student extends Person{
    int mark;
    
    char calculateGrade(){
        char grade = (mark>=90)?'A':(mark>=75)?'B':(mark>=50)?'C':'F';
        return grade;
    }
}

public class prog{
    public static void main(String[] args){
        Scanner in = new Scanner(System.in);
        Student s = new Student();
        s.name = in.next();
        s.age = in.nextInt();
        s.mark = in.nextInt();
        System.out.printf("Name: %s\nAge: %d\nMarks: %d\nGrade: %c",s.name,s.age,s.mark,s.calculateGrade());
    }
}
```

## SAMPLE INPUT:

```text
Jeeva
18
95
```

## OUTPUT:

<img width="497" height="637" alt="Screenshot 2026-09-17 172039" src="https://github.com/user-attachments/assets/57824c38-3a52-4ab5-92fa-256ebcaf674d" />


## RESULT:

Thus, the Java program to implement inheritance and calculate the student grade based on marks was executed successfully.



# Ex.No:3(b) POLYMORPHISM

## QUESTION:

Write a Java program that calculates the area of different shapes using method overloading. Create a class `AreaCalculator` with:

- `area(int side)` for square
- `area(int length, int breadth)` for rectangle
- `area(double radius)` for circle

**For example:**

```text
4
5 6
3.0
```

```text
Area of square: 16
Area of rectangle: 30
Area of circle: 28.274333882308138
```

## AIM:

To implement compile-time polymorphism using method overloading for calculating the areas of different shapes.

## ALGORITHM:

1. Start the program.
2. Create a class `AreaCalculate`.
3. Define three overloaded `area()` methods for square, rectangle, and circle.
4. Read the side of the square.
5. Read the length and breadth of the rectangle.
6. Read the radius of the circle.
7. Call the appropriate overloaded method for each shape.
8. Display the calculated areas.
9. Stop the program.

## PROGRAM:

Program to implement polymorphism using method overloading in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class prog{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        AreaCalculate calc = new AreaCalculate();
        int s = scan.nextInt();
        System.out.println("Area of square: "+calc.area(s));
        int l = scan.nextInt(); int b = scan.nextInt();
        System.out.println("Area of rectangle: "+calc.area(l,b));
        double r = scan.nextDouble();
        System.out.println("Area of circle: "+calc.area(r));
        
    }
}

class AreaCalculate{
    int area(int side){
        return side * side;
    }
    int area(int length, int breadth){
        return length*breadth;
    }
    double area(double radius){
        return Math.PI*radius*radius;
    }
}
```

## SAMPLE INPUT:

```text
4
5 6
3.0
```

## OUTPUT:

<img width="885" height="473" alt="Screenshot 2026-09-17 172347" src="https://github.com/user-attachments/assets/742e1706-c533-4b0a-b39f-6942ac713035" />

## RESULT:

Thus, the Java program to calculate the area of different shapes using method overloading was executed successfully.

# Ex.No:3(C) ABSTRACTION

## QUESTION:

In a secret intelligence facility, encrypted messages are stored as arrays of characters. Each type of agent has a different way to decode these messages. Define an abstract class `Decoder` with a method `decodeMessage(String[] fragments)`.

There are two types of agents:

**AlphaAgent:** Extracts a meaningful string by rearranging the fragments based on even indices first, then odd indices, and then reversing the final result.

**BetaAgent:** Picks all fragments that start and end with the same letter, joins them with `-`, and removes all vowels from the resulting string.

**Input Format:**

- First line: Integer N (number of fragments)
- Next N lines: The string fragments
- Next line: 1 for AlphaAgent, 2 for BetaAgent

**Output Format:**

Decoded message (string)

**For example:**

```text
5
alpha
echo
bravo
oslo
omega
1
```

Output:

```text
osloechoomegabravoalpha
```

For BetaAgent:

```text
4
level
radar
agent
pop
2
```

Output:

```text
lvl-rdr-pp
```

## AIM:

To implement abstraction using an abstract `Decoder` class and different decoding behaviours in `AlphaAgent` and `BetaAgent` subclasses.

## ALGORITHM:

1. Start the program.
2. Create an abstract class `Decoder` with an abstract `decodeMessage()` method.
3. Create `AlphaAgent` that extends `Decoder`.
4. Rearrange even-indexed fragments followed by odd-indexed fragments.
5. Reverse the merged fragment list and join the fragments.
6. Create `BetaAgent` that extends `Decoder`.
7. Select fragments whose first and last characters are equal.
8. Join selected fragments using `-` and remove all vowels.
9. Read the agent type and call the corresponding decoder.
10. Display the decoded message.
11. Stop the program.

## PROGRAM:

Program to implement abstraction using different message decoding agents in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

abstract class Decoder{
    abstract String decodeMessage(String[] f);
}

class AlphaAgent extends Decoder{
    @Override
    String decodeMessage(String[] f){
        
        String[] e = new String[(f.length+1)/2] ;
        int j=0;
        for(int i=0;i<f.length;i+=2)
            e[j++]=f[i];
        
        String[] o = new String[f.length/2];
        j=0;
        for(int i=1;i<f.length;i+=2)
            o[j++]=f[i];
        
        String[] m = new String[f.length];
        j=0;
        for(String i:e)
            m[j++] = i;
        for(String i:o)
            m[j++] = i;
            
        String[] rev = new String[m.length];
        j=0;
        for(int i=m.length-1;i>=0;i--)
            rev[j++] = m[i];
        
        String result = String.join("",rev);
        return result;
    }   
}

class BetaAgent extends Decoder{
    @Override
    String decodeMessage(String[] f){
        
        String select = "";
        for(String s:f){
            if(s.charAt(0)==s.charAt(s.length()-1)){
                if (select.equals(""))
                    select+=s;
                else
                    select += "-"+s;
            }
        }
        
        String result = select.replaceAll("[aeiouAEIOU]","");
        return result;
    }
}

public class prog{
    public static void main(String[] args){
        Scanner s = new Scanner(System.in);
        int n = s.nextInt();
        String[] f = new String[n];
        for(int i=0;i<n;i++){
            f[i]=s.next();
        }
        int type = s.nextInt();
        if (type==1){
            AlphaAgent agent = new AlphaAgent();
            System.out.println(agent.decodeMessage(f));
        }else{
            BetaAgent agent = new BetaAgent();
            System.out.println(agent.decodeMessage(f));
        }
    }
}
```


## OUTPUT:

<img width="653" height="540" alt="Screenshot 2026-09-17 172719" src="https://github.com/user-attachments/assets/9a4c33ba-d7ae-435d-a803-babacd6f92e2" />


## RESULT:

Thus, the Java program to implement abstraction using AlphaAgent and BetaAgent decoders was executed successfully.

# Ex.No:3(D)    INTERFACE

## QUESTION:

You are programming bots that analyze weather data. Each bot must implement a common interface and give a prediction.

**Bot Types:**

- `SunBot`: Predicts `"HOT"` if temperature > 30, else `"MODERATE"`.
- `RainBot`: Predicts `"COLD"` if temperature < 20, else `"WARM"`.

**Input:**

- temperature
- botType (1 for SunBot, 2 for RainBot)

**Output:**

Prediction as a string.

**For example:**

```text
35 1
```

```text
HOT
```

## AIM:

To implement an interface in Java and provide different weather predictions through classes implementing the common interface.

## ALGORITHM:

1. Start the program.
2. Define a `Bot` interface with the `predict(int temp)` method.
3. Create `SunBot` implementing `Bot`.
4. Return `HOT` when temperature is greater than 30; otherwise return `MODERATE`.
5. Create `RainBot` implementing `Bot`.
6. Return `COLD` when temperature is less than 20; otherwise return `WARM`.
7. Read the temperature and bot type.
8. Create the corresponding bot object.
9. Call `predict()` and display the result.
10. Stop the program.

## PROGRAM:

Program to implement an interface using Java weather prediction bots.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

interface Bot{
    String predict(int temp);
}

class SunBot implements Bot{
    public String predict(int temp){
        if (temp>30)
            return "HOT";
        else
            return "MODERATE";
    }
}

class RainBot implements Bot{
    public String predict (int temp){
        if (temp<20){
            return "COLD";
        }else{
            return "WARM";
        }
    }
}

public class prog{
    public static void main(String[] args){
        Scanner  s= new Scanner(System.in);
        int temp = s.nextInt();
        Bot bot;
        if (s.nextInt()==1){
            bot =new SunBot();
        }else{
            bot = new RainBot();
        }
        System.out.println(bot.predict(temp));
    }
}
```

## SAMPLE INPUT:

```text
35 1
```

## SAMPLE OUTPUT:

```text
HOT
```

## OUTPUT:

<img width="353" height="245" alt="Screenshot 2026-09-17 172850" src="https://github.com/user-attachments/assets/9478255e-be76-4212-bfad-11e90d78dba6" />


## RESULT:

Thus, the Java program to implement a common interface for weather prediction bots was executed successfully.


# Ex.No:3(E) INNER CLASS/ ENUM

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
## OUTPUT:

<img width="982" height="322" alt="Screenshot 2026-09-17 173043" src="https://github.com/user-attachments/assets/6cc6c340-5be3-4dea-bf3b-6eb1db5d7d82" />

## RESULT:

Thus, the Java program to create an enum and display season-specific messages using a switch statement was executed successfully.


# Ex.No:3(F) WRAPPER CLASS

## QUESTION:

Write a Java program to demonstrate the use of a Wrapper Class by converting a primitive integer value into an `Integer` object using autoboxing and converting the `Integer` object back into a primitive integer using unboxing. Display both values.

## AIM:

To demonstrate the use of the `Integer` wrapper class and the concepts of autoboxing and unboxing in Java.

## ALGORITHM :

1. Start the program.
2. Read an integer value using `Scanner`.
3. Convert the primitive `int` value into an `Integer` object using autoboxing.
4. Convert the `Integer` object back into an `int` using unboxing.
5. Display the original primitive value and the unboxed value.
6. Stop the program.

## PROGRAM:

Program to demonstrate Wrapper Class using autoboxing and unboxing in Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.Scanner;

public class prog{
    public static void main(String[] args){
        Scanner scan = new Scanner(System.in);
        int number = scan.nextInt();
        Integer obj = number;
        int value = obj;
        System.out.println("Primitive value: " + number);
        System.out.println("Wrapper object: " + obj);
        System.out.println("Unboxed value: " + value);
    }
}
```

## SAMPLE INPUT:

```text
25
```

## SAMPLE OUTPUT:

```text
Primitive value: 25
Wrapper object: 25
Unboxed value: 25
```

## RESULT:

Thus, the Java program to demonstrate the Integer Wrapper Class using autoboxing and unboxing was executed successfully.

