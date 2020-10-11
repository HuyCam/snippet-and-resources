There are 3 type of dependency injections:
1. Constructor injection
2. Field injection
3. Spring setter injection
## Constructor Injection
Technically, you create a private member variable. Then create a constructor to with a parameter to initialize that variable, Spring will automatically call it to initialize. Spring smart. Spring prefer constructor injection over the other two types.
```java
@Component

public class DogsService {

private DogsDao dao;

public List<Dog>  getDogs()  {

System.out.println("DogsService.getDogs called");

return dao.getAllDogs();

}

public void  setDao(DogsDao dao)  {

System.out.println("DogsService setter called");

this.dao = dao;

}

public DogsService(){

System.out.println("DogsService no-arg constructor called");

}

@Autowired

public DogsService(DogsDao dao)  {

System.out.println("DogsService arg constructor called");

this.dao = dao;

}

}
```

## Field injection
is when you use @Autowired or @Qualifier or @Primary.
