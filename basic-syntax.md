[//]: # (title: Basic syntax)

This is a collection of basic syntax essentials for Kotlin with their equivalent in C++.

The Kotlin essentials can be learned over at the [Kotlin Basics track](https://hyperskill.org/tracks/18)
on the JetBrains Academy.

## Semi Colons

Kotlin has largely dispensed with the need for semi-colons to terminate statements. It is encouraged in Kotlin not to use semi-colons. There may be situtations where a semi-colon is required, however, the compiler will 
inform the user where a statement is ambiguous, and will tell you where to insert a semi colon.

```kotlin

fun sum(a: Int, b: Int) : Int
{
   return a + b //No need to terminate a statement with a semi-colon
}
```

In C++ semi colons are ubiquitous and used to delimit statements, declarations, and class and structure definitions.
For example:

``` cpp
int myVariable = 42;   //Semi-colon delimiting a variable
int sum(int a, int b); //Semi-colon delimiting a function prototype

class myClass
{
  int member;    //Semi-colons delimiting members and methods
  void method();
};               //Semi-colon delimiting a class declaration
  
int sum(int a, int b)
{ 
  return a + b;        //Semi-colon deliminting a statement
}
```
### Common Cases for Semi Colons
It is worth noting that semi-colons may still be required.
Some common cases include:
- Enum Classes
```kotlin
enum class MyEnum {
  ENUM_A,
  ENUM_B; 
  // Semi-colon required, as we are adding a function below the list of enum values. 
  //  We must therefore delimit the list. Otherwise this is not necessary.
  
  fun someFunction() {  }
}
```
- Multiple expressions in one line
```kotlin
fun main() {
    var a = 5; var b = 10 // Semi-colon required to separate two expressions in one line
}
```

## Program entry point

An entry point of a Kotlin application is the `main` function.

```kotlin
fun main() {
    println("Hello world!")
}
```

Another form of `main` accepts a variable number of `String` arguments. 

```kotlin
fun main(args: Array<String>) {
    println(args.contentToString())
}
```

The equivalent of these in C++ looks like this:

```cpp
#include  <iostream>
int main()
{
	std::cout << "Hello World" << std::endl;
	return 0; //In C++ main must return an 'int'. This is a quirk it inherited from 'C'
}
```

and

```cpp
#include  <iostream>
int main(int argc, char* argv[])
{
    std::cout << "There are " << argc << " arguments:" << std::endl;
    for (int i = 0; i < argc; ++i) {
        std::cout << argv[i] << std::endl;
    }
}
```
