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


## RESULT:

Thus, the Java program to implement inheritance and calculate the student grade based on marks was executed successfully.
