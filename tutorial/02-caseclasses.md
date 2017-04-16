# Scala case classes

Scala has special syntax for defining 'value objects' (also called Algebraic Data Types - ADTs)

## Define a base trait

* All subclasses of `sealed` traits must be defined in the same file as the trait. (This enables complete pattern matching).

```scala
sealed trait Pet {
  def name: String
}
```

## Define some case classes

```scala
case class Cat(name: String) extends Pet
case class Dog(name: String, breed: String) extends Pet
```

## Objects can extend traits and classes

```scala
  case object OmniPet extends object {
	val name = "OmniPet"
}
```

## Pattern matching

```scala
def breed(pet: Pet): String = {
  pet match {
    case Cat(_) => "Just a cat"
    case Dog(_, breed) => breed
  }
}
```

# Java


 This is the Java version of the case class example. It demonstrates some the code the Scala compiler writes for you when you use case classes. It does not show extractors.

```java
interface Pet {
	String getName();
}
```

```java
class Cat extends Pet {
	private final name;

	public Cat(String name) {
		this.name = name;
	}

	public String getName() {
		return name;
	}

	public String toString() {
		return "Cat(" + name + ")";
	}

	public int hashCode() {
		return name.hashCode;
	}

	@Override
	public equals(Object rhs) {
    if (this == rhs) {
      return true;
    } else if (rhs instanceOf Cat) {
			Cat rhsCat = (Cat) rhs;
			return isEqual(name, rhsCat.name);
		} else {
			return false;
		}
	}
}
```

```java
class Dog extends Pet {
	private final name;
	private final breed;

	public Dog(String name, String breed) {
		this.name = name;
		this.breed = breed;
	}

	public String getName() {
		return name;
	}

	public String getBreed() {
		return breed;
	}

	@Override
	public String toString() {
		return "Dog(" + name + "," + breed +")";
	}

	@Override
	public int hashCode() {
		return name.hashCode + (breed.hashCode * 31);
	}

	@Override
	public equals(Object rhs) {
    if (this == rhs) {
      return true;
    } else if (rhs instanceOf Dog) {
			Dog rhsDog = (Dog) rhs;
			return isEqual(name, rhsDog.name) && isEqual(breed, rhsDog.breed);
		} else {
			return false;
		}
	}
}
```

```java
class Util {
	public static isEqual(Object lhs, Object rhs) {
		if (lhs == null) {
			return rhs == null;
		} else {
			return lhs.equals(rhs);
		}
	}
}
```

# Exercises

1. Use case classes to create a data structure called `OptionalInt` that might hold an `Int` value or might not.
  * Create a trait `OptionalInt`
  * Create a case class `SomeInt` with a single field `value` of type `Int`
  * Create a case object `NoInt`
1. Create a standalone method `valueOrElse` that takes an `OptionalInt` parameter and a default `Int` parameter and returns the `Int` value of the `OptionalInt` or the default if its not set.
1. Use case classes to create a data structure called `ListOfInts` that holds a list of `Int`s, based on the structure of `OptionalInt`
1. Create a standalone method printAll that takes a `ListOfInts` as a parameter and prints each `Int` on its own line. (Hint: Consider using recursion and the return type should be `Unit`)
