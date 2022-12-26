<h1 align = "center">JAVA for Interview</h1>
java is everywhere, it is machine independent ie same code can run on any platform.
java work on principle of WORA = write once and Run anywhere.

## Garbage Collector 
  ```
  Java provide garbage collector , in c and cpp the memory block that we used to create using new keyword
  had to be deleted by programmer using delete keyword , 
  But in java JVM does it automatically.
 
ref1 -----> Memory block 1

ref1 -----> Memory block 2
     
now memory1 is not being pointed by anyone so JVM will free this space as its a garbage.
```

## Compilation & Execution & Installation

``` 

So let Say we have a file called Hello.java now to compile this we need to do
javac Hello.java it will create a Hello.class file (Byte code) and it cant be understood by any OS
         Hello.java  (compilation)  Hello.class

So how to run this when os cant understand this byte code file?
Answer is JVM (java virtual machine) 
JVM has a tool called just-in-time compiler kind of interpreter so it ready line by line from 

Hello.class and provide the translation
of it to OS to execute it.   
 
Note :- JVM is platform dependent and it make byte code (.class file) platform independent. 

Installation :- Do google.

Execution -> java Hello (className to run).

```

## Data Types
```
1) Primitive data types 

2) Non Primitive data type (user defied like class , enum).

Eg of primitive data type.
boolean (1 byte and machine dependent also).
char (2 byte)
byte (1 byte)
short (2 byte)
int (4 byte)
long (8 byte)
float (4 byte)
double (8 byte)

```
## Comments

```
1) single line comment //
2) Block style comment /* text */
3) Documentation style comment  /** text */

```

## Type conversion 
```
1) Implicit type conversion 

2) Explict type conversion

Rule - A small data type can widen itself and type casted to a big data type 
eg. int amount = 3 , float money = amount;  
this is perfectly right , no error is there
but, float amount = 3.4; //  has Error as by default decimal values are of double type.
||y , float a = 2.3f;  int x = a; is wrong ,error
so correction would be type case int x = (int)a;
```
## classes

<details><summary><b>Need</b></summary>

<i>let say we are making a project and we need to store information for a person ie all his attributes like name, age , weight, marital status 
so all of this is of different type so we cannot store all this using one data type. So to solve this prblm we need to use class with different instance member variable.
</i>
</details>
<h4>class</h4>
its a description of an objects property and behaviour.

<h4>Object </h4>

its a real world entity and an instancec of a class.

## Code 
```
class Person{
	private String name;
	private int age;
	private double weight;
	private booleam maaried;
	public void setName(String name) {
		this.name = name;
	}
	public void setWeight(double weight) {
		this.weight = weight;
	}
	public void setMarriedStatus(boolean maaried) {
		this.maaried = maaried;
	}
	public void setAge(int age) {
		this.age = age;
	}
	// methods to read member variable
	public int getAge() {
		return this.age;
	}
	public double getWeight() {
		return this.weight;
	}
	public String getName() {
		return this.name;
	}
	public boolean isMaaried() {
		return this.maaried;
	}
}

```
<h3>Note</h3>

Person will not be allocated memeory till now as we have not created object of person;

## Object creattion 
```
use new keyboard to create a object 
Person p = new Person();

```
<h5>Note</h5>

Here p is a reference variable of person type and its not a object and statement new Person() , in reality create the object of person type.
and reference variable p will point to that person obhect;

## static Members :-

wrting static keyword to any instance member variable or method will make that member a static member.

<h2>Code </h2>

```
static int x;  // static variable 
public static void fun1() {
  // static method
}

```
<h5>Note</h5>

But there is no static local variable in java
```
public static void fun1() { 
	static int x;// error
}
```

But we can make static inner class.
<h3>Code</h3>

```
class outerclass {
	static class innerclass {
       // Inner class
	}
}

```
## Some points

Static variable are only created once

<details><summary><b>How to Access it</b></summary>

```

ClassName.variable_name
eg Person.name // if name is static variable for person class.

```
</details>


<h5>Note</h5>

Static methods can access only static variable.

<details><summary><b>Need</b></summary>

```
Let consider eg of bank each person have different amount , name but rateOfInterest function will be same for each person so we can make it static method , it will save memory too.
```

</details>

## Wrapper class 
due to primitive data type java is not fully object oriented.
But we have Wraper class which convert the primitive data type to its wrapper class 

```
int -> Integer
double -> Double
float -> Float
boolean -> Boolean
etc...

```

<details><summary><b>Reason to use Wraper class</b></summary>

```
List , and other ADT doest not work on primitive data type so we need to insert a wraper object in them as all these ADT extends Collection class which only work on objects.
eg PriorityQueue<Integer> que = new PriorityQueue<>();

```
</details>
