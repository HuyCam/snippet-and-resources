# Autoboxing, Unboxing, ArrayList, LinkedList
## ArrayList
`ArrayList<String> names = new ArrayList<String>(); `
* Get a value or object at a certain position: 
```java
int position = 3;
names.get(position); 
```
* Add a value or object at the last position of the ArrayList or at a certain position:
```java
names.add("huy");
names.add(3, "huy");
```
* Modify a value or an object at a certain position:
```java
names.set(3, "tan");
```
* Remove a value or anobject at a certain position:
```java
names.remove(3);
```
* Get a position of an object with provided certain value of that object, **Note that to use with custom type, you need to overide equals() and hashCode() so the indexOf will yield correct result**
```java
names.indexOf("huy");
```
## Autoboxing and unboxing
Autoboxing is the automatic conversion that the Java compiler makes between the primitive types and their coresponding object wrapper classes. For example, converting an int to an Integer, a double to a Double and so on. If the conversion goes the other way, this is called unboxing.
Example of autoboxing: `Character ch = 'a';`
```java
List<Integer> li = new ArrayList<>();
for (int i = 1; i < 50; i += 2)
    li.add(i);
```
is equal to
```
List<Integer> li = new ArrayList<>();
for (int i = 1; i < 50; i += 2)
    li.add(Integer.valueOf(i));
```
***Iteger.valueOf(i)*** convert a integer to a Class of Integer.
***someInteger.intValue() / 2*** will get the value of that integer but you can also write as ***someInteger / 2***. This is called unboxing.

## Comparison in Java
Java do shallow comparison by default which check if two object refer to the same object. To make more sophisticate comparison. You need to override equals function

## Override equals and hashCode for indexOf()
When you run **indexOf()**, it will run **equal()** to compare two object. So when you have custom type object, it is best to override **equal()** and **hashCode()** methods. Even though indexOf don't use **hashCode()** but it is recommanded to override it too to avoid later unwanted bug.

## Inner Class
Inner class is class that reside inside an outer class. Inner class can use outer class properties and methods no matter if those methods and properties are private. If there is a variable name in a inner class that is the same as its outer class. That variable will shawdow the outer class variable.
```java
public class Gearbox {
    private ArrayList<Gear> gears;
    private int maxGears;
    private int currentGear = 0;

    public Gearbox(int maxGears) {
        this.maxGears = maxGears;
        this.gears = new ArrayList<>();
        Gear neutral = new Gear(0, 0.0);
        this.gears.add(neutral);
    }

    public class Gear {
        private int gearNumber;
        private double ratio;

        public Gear(int gearNumber, double ratio) {
            this.gearNumber = gearNumber;
            this.ratio = ratio;
        }

        public double driveSpeed(int revs) {
            return revs * (this.ratio);
        }
    }
}
```
### Instantiate an object of inner class
```
Gearbox mcLaren = new Gearbox(6);
    // create instance of subclass
    Gearbox.Gear first = mcLaren.new Gear(1, 12.3);
    Gearbox.Gear second = mcLaren.new Gear(2, 15.4);
    System.out.println(first.driveSpeed(1000));
```

Notice the **mcLaren.new** synstax to create new Gear.
