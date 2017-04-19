# Collections

## Tuples

```scala
val oneValue = (1)
val twoValues = (1, "two")
val threeValues = (1, "two", false)
```

## List

```
val emptyList = Nil
val listOfOne = "One" :: Nil
val listOfTwo = "One" :: "Two" :: Nil
```

```
listOfTwo map { s => s.length }
```

## Option

```
def displayAge(maybeAge: Option[Int]): String {
  maybeAge.map(a => s"${a} years old").getOrElse("unknown")
}

displayAge(Some(21))

displayAge(None)
```
