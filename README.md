# IntelliJ Learning Session

We'll be working with IntelliJ's default shortcuts. Case for using defaults: it makes collaboration easier (e.g.: for
pair programming and knowledge sharing).

In this learning session we'll work on a simple TDD example. Through this example we'll find out useful shortcuts, tips,
and tricks.

We'll be writing a DEP file parser. A mock DEP file is in [`src/test/java/resources/sample.dep`](src/test/java/resources/sample.dep).

We'll try to avoid using the mouse as little as possible. 

Let's get started.

## Getting started

1. Clone this project.

1. Navigate into the cloned directory and verify that the project builds and runs:

    ```bash
    gradle run
    ```
    
    Expected output:
   
    ```
    > Task :run
    Hello world!
    
    
    BUILD SUCCESSFUL in 1s
    2 actionable tasks: 2 executed
    ```

1. Open IntelliJ and click `File -> Open...`.

1. Find this project and open it.

1. Press `Ctrl+N -> main` (btw, you can use `Shift Shift` too for this) and open the file `Main.java`. Then press 
    `Ctrl+Shift+F10`.

1. The application should build and run.


## Write the first test...

We're going to do some simple TDD now. We'll do the red, green, refactor cycle.

Let's start.

Create the Java file `DepParserTest.java` file in the test sources directory.

You can navigate to the directory via `Ctrl+Shift+N -> t/j/` and then `Alt+Insert`.

Write the first test function to parse parsing empty DEP files. It should throw an exception.


Deliberate mistakes:

- write `DepParser.from_string`. We'll rename `from_string` to `fromString` with refactoring.


We will use:

- Find everything, action, file shortcuts (like`Shift+Shift`, or `Ctrl+Shift+A`, or `Ctrl+Shift+N`, etc.),

- refactoring to create classes and methods that don't exist yet (lots of `Alt+Enter`),

- splitting and moving editor tabs,

- `Ctrl+Shift+Enter`,

- static imports,

- remove the pesky "Make package-private" inspection,

- running tests with `Ctrl+Shift+F10`,

- talk about run configurations (`Alt+Shift+F10`),

- navigating in code (`Alt+B`, `Ctrl+Alt+F7`, `Ctrl+U`, `Ctrl+Alt+Left|Right`, `Ctrl+Shift+Backspace`)

- automatic rerun of tests (place where `Shift+Shift` fails me: search for `build proj auto`),

- live templates (how to: select text, `Ctrl+Shift+A -> Save as Live Template`).

## Refactor

Refactor `from_string` to `fromString`.

We will use:

- `Ctrl+Alt+Shift+T` to find out what refactoring actions we can take in the context,

- `Shift+F6` to rename the function.


## Write the second test...

Write the test using the live template. Use the `assertEquals` static function.

We will write the test for `getName` on the parsed Dep file.

We will use:

- `Ctrl+Space Space` to bring up all static methods,

- Then we will use `Alt+Enter` to import it statically,

- `Ctrl+F6` to change the signature of the `fromString` function,

- We will use the "Problems" tab to fix the problems introduced by the signature change,

- `Alt+4` to open the running tests,

- run all tests not just the specific one,

- Use `Ctrl+Alt+T` to surround the exception with `if`,

- Use `Ctrl+Shit+T` to go to  or generate tests.





# Useful resources

- [IntelliJ shortcut cheatsheet](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)