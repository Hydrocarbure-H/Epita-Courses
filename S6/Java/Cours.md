#Java - Piscine

`Notes de cours par Thomas Peugnet`.

*Objectif : Synthétiser la syntaxe de base du Java*.

# Chaines de caractères

## Déclaration

```java
public class Main {
  public static void main(String[] args) {
    char[] hello = { 'H', 'e', 'l', 'l', 'o' };
    var helloStr = new String(hello);
    var world = "World!";
    var empty = new String(); // Builds an empty String ("")
    var goodBye = new String("Goodbye");
    var worldCpy = new String(world);
  }
}
```

## Manipulation

```java
var tooManyWhitespaces = " I just ";
var bigString = "I wanna feel sunlight on my face.";
var lowerCase = "help you";
System.out.print(tooManyWhitespaces.strip()); // Delete spaces...
System.out.print(bigString.substring(1, 8));
System.out.println(lowerCase.toUpperCase());
```

## Comparaison

```java
var myString = "Don't be afraid.";
var myStringCpy = new String(myString);
System.err.println(myString == myStringCpy); // false
System.out.println(myString.equals(myStringCpy)); // true
// However...
var myOtherString = "Don't be afraid.";
// myString and myOtherString are string literals, they refer to the same memory area.
System.out.println(myString == myOtherString); // true
```

## Ajout

```java
var stringBuilder = new StringBuilder("Hello ");
stringBuilder.append('w');
stringBuilder.append(0); // Appends '0', not (char)0!
stringBuilder.append((char)114); // 114 is the ASCII value of 'r'
stringBuilder.append("ld!");
System.out.println(stringBuilder.toString());
var myString = new String(stringBuilder);
System.out.println(myString);

//
// Using '+' may work, but is not recommanded
//
```



# Listes

```java
var myList = new ArrayList<Integer>();
// Appends the given list at the end of myList.
myList.addAll(Arrays.asList(1, 3, 5, 7, 9));
myList.add(2); // Appends 2 at the end of myList
myList.remove(3); // Remove the element at index 3 (7)
myList.set(0, 47); // Sets the value at index 0 to 47
final var myListSize = myList.size(); // Number of elements in the list
// Print the content of myList
for (var index = 0; index < myListSize; index++) 
{
  var valAt = myList.get(index); // Gets the element at the given index
  System.out.println(valAt);
}
```

## Itération

```java
var myList = new ArrayList<Integer>(Arrays.asList(1, 3, 5, 47, 9));
for (var value : myList) 
{
	System.out.println(value);
}
```

# Annotations

```java
@Annotation
public void MyMethod() { ... }

@Authors(
  name = "Name"
  date = 11/04/2018
)
class MyClass() { ... }
```

##`@Override`

```java
public class Example
{
	@Override
  public String toString()
  {
    // this is a valid override
    return super.toString() + "Testing annotation name: `Override`";
  }
}
//
//In the previous example, toString is a method 
//of the Object class, so we can override it 
//(as every class has Object as a superclass)
//
```

`@Override` permet de réécrire une méthode qui est déjà présente dans une classe supérieure.



# Keywords

## `extends, private, protected`

```java
public class Main 
{
  public static class ParentClass 
  {
    protected String inheritedString = "Inheritance is cool!";
    public void printPublic() 
    {
      System.out.println("Hello world!");
    }
    protected void printProtected() 
    {
      System.out.println("Hello subclasses!");
    }
    void printDefault() 
    {
      System.out.println("Hello package!");
    }
    private void printPrivate() 
    {
      System.err.println("Hello myself...");
    }
  }
  public static class ChildClass extends ParentClass 
  {
    public void run() 
    {
      printPublic(); // OK
      printProtected(); // OK
      printDefault(); // OK
      printPrivate(); // Error: printPrivate has private access in ParentClass
      System.out.println(inheritedString);
    }
  }
  public static void main(String[] args) {
    var child = new ChildClass();
    child.run();
  }
}
```

# Polymorphisme

````java
public class Main {
  public static class ParentClass 
  {
    public void inheritedMethod() 
    {
      System.out.println("Parent method");
    }
  }
  public static class ChildClass extends ParentClass 
  {
    public void inheritedMethod() 
    {
      System.out.println("Child method");
    }
  }
  public static void main(String[] args) 
  {
    ParentClass parent = new ParentClass();
    ChildClass child = new ChildClass();
    /* Polymorphism: ParentClass is actually polymorphicChild's static type
        * (compile-time).
        * Its dynamic type (runtime) is ChildClass.
        */
    ParentClass polymorphicChild = new ChildClass();
    parent.inheritedMethod();
    child.inheritedMethod();
    		/* Dynamic dispatch: call the method from the dynamic type,
    		 * since methods are virtual by default.
        */
    polymorphicChild.inheritedMethod();
  }
}
````

Ce qui donnera : 

```
Parent method
Child method
Child method
```

# Utilisation de `Final`

## Classes

```java
public class Main {
  public static final class FinalClass { }
  public static class BrokenClass extends FinalClass {
    // Error: Cannot inherit from the final class FinalClass
  } 
}
```

## Fonctions

```java
public class Main {
  public static class ParentClass {
    public final void finalMethod() { System.out.println("Final method");
    } 
  }
  public static class ChildClass extends ParentClass { @Override
    public void finalMethod() {
      // Error: Cannot override final method finalMethod from ParentClass System.err.println("Attempting to override final method");
    } 
  }
}
```

## Attributs

```java
public class Main {
  public static class MyClass {
    public final int myInt = 0;
    public void myMethod() {
      myInt++; // Error: Cannot assign a value to final variable myInt
    } 
  }
}
```

*`Final` correspond grossièrement à `const`en C*.

## Variables

```java
public class Main {
  public static void main(String[] args) {
    final String assignedAtDeclaration = "Our only hope is "; final String blankFinal;
    if (args.length != 1) {
      blankFinal = "to recode everything!";
    } else {
      blankFinal = args[0];
    }
    System.out.println(assignedAtDeclaration + blankFinal);
  }
}
```

*Note : On peut déclarer une variable `final` sans valeur de base, et lui en attribuer une après un `if, switch, etc.`*.

# Objets Génériques

```java
public class MyGenericObject<T> { 
  private T obj;
  public void setObj(T obj) { 
    this.obj = obj;
  }
  public T getObj() { 
    return obj;
  } 
}

/**/

public static void main(String[] args) { 
  MyGenericObject<String> str = new MyGenericObject<>(); // ...
}
```

## Exemple d’utilisation : création d’une structure `Stack`

```java
public class Stack<ELEMENT_TYPE> {
  private List<ELEMENT_TYPE> list = new ArrayList<>();
  // The elements we can push on the stack can only be of type ELEMENT_TYPE
  void push(ELEMENT_TYPE element) { 
    list.add(0, element);
  }
  ELEMENT_TYPE pop() {
    ELEMENT_TYPE result = list.get(0); list.remove(0);
    return result;
  }
}
```

# Collections

## Listes

> • **ArrayList**: A simple vector with lots of methods. Can be used as a **LIFO**. It is optimized for get O(1), but O(n) at worst for insertion/deletion. An ArrayList increases its internal array size by 50 percent when it runs out of space.
>
> • **LinkedList**: Can be used as a **FIFO**. It is optimized for insertion/deletion O(1), but O(n) at worst for get.
>
> • **Vector**: ArrayList’s thread-safe counterpart. As it has to lock, it is slower: therefore, we advise you to use **ArrayList** whenever possible for performance reasons. A Vector doubles the size of its internal array when it runs out of space.
>
> • **Deque**: stands for Double-Ended Queue. The name speaks for itself: it is a linear collection supporting access, insertion and removal at both ends.

## Maps

> **Maps** associate a **key** to a **value**. They are sometimes called **associative arrays**.
>
> • **HashMap**: Uses a hash method. Insertion, lookup and deletion are executed in constant time
>
> O(1) but linear time O(n) is required for iteration.
>
> • **ConcurrentHashMap**: HashMap’s thread-safe counterpart. Just like Vector with ArrayList, ConcurrentHashMap is slower than HashMap: use the latter whenever possible. Moreover, the ConcurrentHashMap allows neither keys nor values to be null.
>
> • **TreeMap**: Uses a balanced tree (depending on the underlying implementation). Therefore, this map is guaranteed to be ordered, but it cannot afford constant-time performance where HashMap can: all basic operations, such as get, put and remove, are executed in O(log n).

## Sets

> A **set** is a **container** in which, compared to lists, **ordering is less important than existence**. A list can contain the **same element several times**, whereas a set can’t say more than “the element is (or isn’t) present”. Therefore, just like **maps**, some sets do not have any ordering. This makes them **more efficient than lists** for search operations.
>
> • **HashSet**: Implemented with a hash method (actually a HashMap): no ordering. Basic operations are executed in constant-time O(1).
>
> • **TreeSet**: Implemented with a balanced tree (actually a TreeMap). Basic operations are executed in logarithmic-time O(log n), but we can safely iterate upon a TreeSet. TreeSet is an ordered container.
>
> • **LinkedHashSet**: Extends **HashSet**, but maintains a doubly-linked list running through its entries. This way, the order of iteration across the Set is the order in which the elements were inserted into the Set.
>
> Unfortunately, there is no built-in thread-safe set amongst Java collections. You can however make an existing set thread-safe by using Collections#synchronizedSet.

# Exceptions

```java
public static long factorial(int n) throws InvalidNumberException {
  if (n < 0) {
    throw new InvalidNumberException(n); }
  else {
    return (n == 0) ? 1 : n * factorial(n - 1); 
  }
}
```

```java
public static void main(String[] args) { 
  int i = 5;
  while (true) { 
    try {
      final long fact = factorial(i); System.out.println(fact);
      i--;
    } 
    catch (InvalidNumberException e) { 
      e.print();
      break; 
    }
  } 
}
```

## Création de ses propres exceptions

```java
public class Main {
  public static class InvalidNameException extends Exception{
    public InvalidNameException() { 
      System.err.println("Empty name");
    } 
  }
  public static class InvalidAgeException extends Exception { 
    public InvalidAgeException(final int age) {
      System.err.println("Invalid age: " + age);
    }
  }
  public static class Person { 
    public final String firstName; 
    public final String lastName; 
    public final int age;
    public Person(final String firstName, final String lastName, final int age) throws InvalidNameException, InvalidAgeException { // Multiple throws
      if (firstName.isEmpty() || lastName.isEmpty()) {
        throw new InvalidNameException();
      } 
      else if (age < 0) {
        throw new InvalidAgeException(age); 
      }
      this.firstName = firstName; 
      this.lastName = lastName; 
      this.age = age;
    } 
  }
  public static void main(String[] args) { 
    try {
      final var myPerson = new Person("Papy", "Russe", -21); }
    catch (InvalidNameException e) { 
      // Multiple catch blocks
      e.printStackTrace();
    } catch (InvalidAgeException e) {
      e.printStackTrace();
    }
  } 
}
```

# Dates, Heures & Minutes

```java
DayOfWeek dayOfWeek = DayOfWeek.FRIDAY; 
dayOfWeek.getDisplayName(TextStyle.FULL, Locale.getDefault()); // Friday
Month month = Month.JUNE; 
month.getDisplayName(TextStyle.SHORT, Locale.FRANCE); // juin

LocalDate localDate = LocalDate.of(2006, 7, 9); // 9 July 2006 
localDate.getDayOfWeek(); // Sunday

LocalDate localDate = LocalDate.of(2006, 7, 9); // 9 July 2006
YearMonth.from(localDate); // 2006-07 
MonthDay.from(localDate); // --07-09 
Year.from(localDate); // 2006
```

```java
// Static method that gives the current LocalDateTime
LocalDateTime currentDateTime = LocalDateTime.now();
// Static method to instantiate a LocalDateTime for a known date
LocalDateTime localDateTime = LocalDateTime.of(2021, 4, 7, 11, 42);
// Getters on each field 
localDateTime.getHour()); // 11 
localDateTime.getMonth(); // APRIL 
localDateTime.getDayOfWeek(); // WEDNESDAY 
localDateTime.getDayOfMonth(); // 7 
localDateTime.getDayOfYear(); // 97
// Methods to compare LocalDateTime objects 
localDateTime.isEqual(currentDateTime); // false
// Methods for adding or subtracting the specified quantity of a field 
localDateTime.plusDays(2); // 2021-04-09T11:42 
localDateTime.minusMinutes(72); // 2021-04-07T10:30
// Methods to modify a specific field 
localDateTime.withHour(23); // 2021-04-07T23:42 
localDateTime.withMonth(1); // 2021-01-07T11:42

ZoneId zoneId = ZoneId.of("Europe/Paris"); // Europe/Paris
// These two classes can be combined with a LocalDateTime
ZonedDateTime zonedDateTime = ZonedDateTime.of(localDateTime, zoneId); // 2021-04 􏰀→ 07T11:42+02:00[Europe/Paris]
```

## Parsing

```java
LocalDateTime localDateTime = LocalDateTime.parse("2021-04-07T11:42");
LocalDate date = LocalDate.parse("07-04-2021", DateTimeFormatter.ofPattern("MM-dd-yyyy")); date.format(DateTimeFormatter.ofPattern("yyyy-dd-MM"); // 2021-04-07
```

# Files

```java
public class Main {
  public static void main(String[] args) {
    Path file = Paths.get("mystery.txt");
    try {
      // Read mystery.txt
      List<String> lines = Files.readAllLines(file);
      List<String> writeLines = Arrays.asList("This", "is", "a", "message");
      Files.write(file, writeLines, Charset.forName("UTF-8"));
    } catch (IOException e) { 
      e.printStackTrace();
    }
  } 
}
/**/
// Reading line by line
/**/
public class Main {
  public static void main(String[] args) {
    String fileName = "file-file-file.txt";
    //read file into stream, try-with-resources
    try (Stream<String> stream = Files.lines(Paths.get(fileName))) { 
      stream.forEach(System.out::println);
    } catch (IOException e) { 
      e.printStackTrace();
    } 
  }
}
```

## Classe `File`

```java
// Get current working directory path
String cwd = new File("").getAbsolutePath(); System.out.println("Current location : " + cwd);
// Create an empty file in current working directory
File file = new File("file-at-bad-location.txt"); if (!(file.createNewFile()))
  System.out.println("Can't create new file at " + cwd);
// Create a new directory in current working directory
File newDir = new File("newDir"); if (!newDir.mkdirs())
  System.out.println("Can't create directory at " + cwd);
System.out.println(newDir.getAbsolutePath());
// Move file-at-bad-location.txt in the new directory and rename it
if (!(file.renameTo(new File(newDir.getAbsolutePath() + File.separator + "file-at-good- 􏰀→location.txt"))))
  System.out.println("Can't move file to " + newDir.getAbsolutePath());
// Create several nested directories
if (!new File(newDir.getAbsolutePath() + File.separator + "subDir/subSubDir/subSubSubDir"). 􏰀→mkdirs())
  System.out.println("Can't create directories");
// Unfortunately, you cannot remove a non empty directory in java in one
// shot. You must remove all its contents first and then remove it.
boolean deleteDirectory(File file) { 
  File[] contents = file.listFiles(); if (contents != null) {
    for (File f : contents) { 
      deleteDirectory(f);
    } 
  }
  return file.delete(); }
deleteDirectory(newDir);
```

# Streams

```java
Stream.of(1, 2, 3, 4, 5)
  	.filter(i -> i < 3);
// The stream now contains (1, 2)
// Another way to obtain a stream, by using collections
ArrayList<Integer> list = new ArrayList<>(Arrays.asList(1, 2, 3, 4, 5)); 
var res = list.stream().filter(i -> i < 3);
// The res stream contains (1, 2)
Stream.of(1, 2, 3, 4, 5)
    .map(i -> i + 1);
// The stream now contains (2, 3, 4, 5, 6)
Stream.of(3, 5, 2, 1, 4)
    .sorted();
// The stream now contains (1, 2, 3, 4, 5)
Stream.of("ah", "one", "two", "three")
    .sorted((i, j) -> i.compareTo(j));
// The stream now contains ("ah", "one", "three", "two")
List<Integer> list = Stream.of(1, 2, 3, 4, 5)
    .filter(i -> i < 3)
    .collect(Collectors.toList());
```

# JSON

*JavaScript Object Notation*

Ajout de la bibliothèque `Jackson` au projet `Maven` : 

- Ajout de cette partie dans la liste des dépendances du fichier `pom.xml`.

```xml
<dependency>
  <groupId>com.fasterxml.jackson.core</groupId>
  <artifactId>jackson-databind</artifactId>
  <version>2.10.0</version>
</dependency>
```

```java
public class Person { 
  public String firstName; public String lastName; public int age;
  public Person(String firstName, String lastName, int age) { 
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
  }
  // Jackson needs a default constructor to initialize the object
  public Person() {
  } 
}

/**/

final ObjectMapper mapper = new ObjectMapper();
final Person person = new Person("Jackson", "Me", 42); f
inal String jsonString = mapper.writeValueAsString(person);

/**/

final ObjectMapper mapper = new ObjectMapper();
final String jsonString = "{\"firstName\" : \"Jackson\", \"lastName\" : \"Me\", \"age\" : 42}";
final Person person = mapper.readValue(jsonString, Person.class);
```

