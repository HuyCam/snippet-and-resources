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
```java
* Get a position of an object with provided certain value of that object, ***Note that to use with custom type, you need to overide equals() and hashCode() so the indexOf will yield correct result**
```java
names.indexOf("huy");
```
