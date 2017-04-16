# Scala basics

## Define a method

* `: Int` specifies the type of the parameters and return type of the method
* The method's return value is the value of the last expression

```scala
def add(a: Int, b: Int): Int = {
  a + b
}
```

## Define a method without parentheses

```scala
def add(a: Int, b: Int): Int = a + b
```


## Define a value

* The type is inferred from expression

```scala
val name = "Iain"
```

## Define a variable :-(

* Again type is inferred (but be careful of polymorphism)

```scala
var location = "workday"
```

## Print a value

```scala
println("Any string here")
```

# Flow control

## If statement

```scala
if (name == "Iain") {
  println("Its me")
}
```

## If expression

* if expressions require an `else` clause, and can return a value

```scala
val who = if (name == "Iain") {
  "Me"
} else {
  "Not me"
}
```

## While loop

```scala
var i=0
while(i < 10) {
  println(s"Iteration $i")
  i += 1
}
```

## For loop

```scala
for(i <- 0 to 9) {
  println(s"Iteration $i")  
}

for(i <- 0 until 10) {
  println(s"Iteration $i")  
}
```

# Classes and objects in Scala

## Define a class

```scala
class Pet(name: String)
```

## Define an abstract class

```scala
abstract class Pet(name: String)
```

## Define a subclass

```scala
class Cat(name: String) extends Pet(name)
class Dog(name: String, breed: String) extends Pet(name)
```

## Create a method
```scala
class Dog(name: String, breed: String) extends Pet(name) {
  override def toString: String = s"Dog($name, $breed)"
}
```

## Define an accessor

```scala
class Dog(name0: String, breed0: String) extends Pet(name) {
  override def toString: String = s"Dog($name0, $breed0)"
  def name: String = name0
}
```

## Scala objects

* Classes do not have static members in Scala and everything is an object, so static methods and data are defined in objects
* These are like singletons
* objects hold values and methods

```scala
object Pets {
  val moggy = new Cat("moggy")
  val princess = new Dog("princess", "boxer")

  def someMethod: String = ???
}
```
