
# Women Who Code Scala Intro

This is a short introduction to Scala for the Women Who Code meet up in Workday's Dublin office.

This introduction is based on the book [Atomic Scala](http://www.atomicscala.com/) by Bruce Eckel and Dianne Marsh.  The fist half of this book is available free online.

## The Plan

* We are going to setup a Scala development environment.
* Then then we will explore basic Scala syntax in the REPL (Scala Shell).
* Next we will look at classes and objects.
* Before finishing looking at collections and functional programming.

## Development Environment

To keep things simple I am going to use git, sbt and the atom editor for this introduction. There is also a docker image containing the code and a full command-line development environment.

### Java

Scala is a JVM language you will need to install the [Java Development Kit](https://www.java.com/en/download/help/index_installing.xml) to follow this tutorial. If installing this for the first time select version 8.  You can also use version 7 if its installed already.


### Git

The source code for this tutorial is available on [github](https://github.com/IainHull/women-who-code-scala-intro). Ensure that git is installed on you local machine, there are [detailed instructions here](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

Then to download the code use the following command line

```
git clone https://github.com/IainHull/women-who-code-scala-intro.git
cd women-who-code-scala-intro
```

TODO

If you cannot use Git you can download the source code for each step as a [zip file here](https://github.com/IainHull/women-who-code-scala-intro/releases/download/steps-0-to-5/women-who-code-scala-intro.zip).

### SBT

SBT is the Scala build tool once it install and configure our scala commandline environment.

Full details on how to [download and install SBT are here](http://www.scala-sbt.org/0.13/docs/Setup.html). If you do not want to install SBT onto your system follow the [manual instructions](http://www.scala-sbt.org/0.13/docs/Manual-Installation.html) to download and run SBT from a temp directory.

Run SBT from the command-line, then in the SBT shell run `compile` and `console`.  Console runs the Scala REPL.  To exit the REPL type `:quit`.  To exit the SBT shell type 'exit'

```
$ sbt

> compile

> test

> console

scala> :quit

> exit
```

### Atom

I am using the [Atom](https://atom.io/) editor, its a friendly open source editor. You are free to use what ever IDE or editor you like.

### Docker  

Pull and run the women-who-code-scala-intro docker image.  Be warned this image is about 800Mb, **download this in advance**.

```
docker pull iainhull/women-who-code-scala-intro
docker run -it iainhull/women-who-code-scala-intro
```

Now run sbt from the docker command-line.

```
# sbt
```

## Tutorial

1. [Basics](tutorial/01-basics.md)
1. [Case classes](tutorial/02-caseclasses.md)

## FAQ

#### Do I need to know Scala?

Absolutely not. Experience with any object oriented or functional language will do.  I will introduce all the scala features as we use them.

#### How functional is this?

Using types for correctness is common functional technique, but it can just as easily be applied to object oriented code.  The code we will be working on will be very simple, but time allowing we will explore more advanced functional concepts like type-classes.

#### What should I bring?

A laptop and a sense of adventure.

#### What tools will we use?

The source code we will hack on will be provided in a github repo.


# License

All code and documentation is licensed under the [Creative Commons Attribution 3.0 Unported License](https://creativecommons.org/licenses/by/3.0/).  See LICENSE.md for more information.
