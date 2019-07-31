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
***someInteger.intValue() / 2*** will get the value of that integer but you can also write as ***someInteger / 2****. This is called unboxing.
