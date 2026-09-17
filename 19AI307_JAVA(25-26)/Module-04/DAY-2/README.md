# Ex.No:4(B)  IMPLEMENT SOLID PRINCIPLES IN JAVA PROGRAM

## QUESTION:

Implement the Observer pattern for a smart-city Air Quality Index (AQI) sensor network. Create a `SensorNetwork` as the subject and `SmartController` classes as observers. The controllers are `GreenZoneController`, `AlertZoneController`, and `DangerZoneController`, each reacting only to its corresponding AQI range.

- `GreenZoneController`: AQI < 100
- `AlertZoneController`: AQI between 100 and 200
- `DangerZoneController`: AQI > 200

When the sensor network receives an AQI reading, notify the registered observers and allow only the relevant controller to take action.

## AIM:

To implement the Observer design pattern in Java by allowing AQI controllers to receive and process sensor notifications according to their assigned ranges.

## ALGORITHM:

1. Start the program.
2. Define an `Observer` interface with the `check()` method.
3. Create `GreenZoneController`, `AlertZoneController`, and `DangerZoneController` classes implementing the interface.
4. Create the `SensorNetwork` subject with a list of observers.
5. Register the three controllers with the sensor network.
6. Read the number of AQI readings.
7. Read each sensor ID and AQI value.
8. Display the sensor reading and notify all registered observers.
9. Each controller checks the AQI range and reacts only when its condition is satisfied.
10. Stop the program.

## PROGRAM:

Program to implement the Observer pattern for an AQI monitoring system using Java.

**Developed by:** ISRAVEL Y  
**RegisterNumber:** 212225240054

## SOURCE CODE:

```java
import java.util.*;

interface Observer {
    void check(int aqi, String sensorId);
}

class GreenZoneController implements Observer {
    public void check(int aqi, String sId){
        if (aqi<100){
            System.out.println("[GreenZoneController]: AQI is good at Sensor "+sId+". No action needed.");
        }
    }
}

class AlertZoneController implements Observer {
     public void check (int aqi, String sId){
         if (aqi>=100 && aqi<=200){
             System.out.println("[AlertZoneController]: Moderate AQI at Sensor "+sId+". Send public health alert.");
         }
     }
}

class DangerZoneController implements Observer {
     public void check (int aqi, String sId){
         if(aqi>200){
             System.out.println("[DangerZoneController]: Critical AQI at Sensor "+sId+"! Trigger lockdown protocol.");
         }
     }
}

class SensorNetwork {
    private List<Observer> observers = new ArrayList<>();
    
    public void register(Observer observer){
        observers.add(observer);
    }
    
    public void receiveData(String id, int aqi){
        System.out.println("Sensor "+id+" reports AQI: "+aqi);
        for(Observer o:observers){
            o.check(aqi,id);
        }
    }
}

public class prog {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        SensorNetwork network = new SensorNetwork();

        network.register(new GreenZoneController());
        network.register(new AlertZoneController());
        network.register(new DangerZoneController());

        int n = sc.nextInt(); sc.nextLine();
        for (int i = 0; i < n; i++) {
            String[] parts = sc.nextLine().split(" ");
            String id = parts[0];
            int aqi = Integer.parseInt(parts[1]);
            network.receiveData(id, aqi);
        }
    }
}
```

## SAMPLE INPUT:

```text
3
S1 75
S2 120
S3 250
```

## SAMPLE OUTPUT:

```text
Sensor S1 reports AQI: 75
[GreenZoneController]: AQI is good at Sensor S1. No action needed.
Sensor S2 reports AQI: 120
[AlertZoneController]: Moderate AQI at Sensor S2. Send public health alert.
Sensor S3 reports AQI: 250
[DangerZoneController]: Critical AQI at Sensor S3! Trigger lockdown protocol.
```

## OUTPUT:


## RESULT:

Thus, the Java program to implement the Observer pattern for an AQI sensor network was executed successfully.