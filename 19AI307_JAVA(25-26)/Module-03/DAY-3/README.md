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

## SAMPLE INPUT 1:

```text
5
alpha
echo
bravo
oslo
omega
1
```

## SAMPLE OUTPUT 1:

```text
osloechoomegabravoalpha
```

## SAMPLE INPUT 2:

```text
4
level
radar
agent
pop
2
```

## SAMPLE OUTPUT 2:

```text
lvl-rdr-pp
```

## OUTPUT:


## RESULT:

Thus, the Java program to implement abstraction using AlphaAgent and BetaAgent decoders was executed successfully.
