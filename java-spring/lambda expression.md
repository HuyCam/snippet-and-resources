# Lambda Expression
Lambda expression is to express a instance of Funcntional Inteferface. Why? Usually, for an Functional Interface, it has only one abstract method. People usually create a anonymous class for it so they don't have to define a class that implements it, that wast too much time and space. Like this Consumer functional interface

```java
Consumer<Integer> traverse = new Consumer<Integer>() {

	@Override
	public void accept(Integer t) {
	System.out.println(t + 1);
		
	}
};
```

The above example is the declaration of an anonymous class.
Now let replace lambda expression with it

```java
Consumer<Integer> traverse = (Integer t) -> System.out.println(t + 1);
```

See now it shorter.
