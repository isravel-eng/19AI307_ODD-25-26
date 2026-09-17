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
