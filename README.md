# IntelliJ Learning Session

We'll be working with IntelliJ's default shortcuts. Case for using defaults: it makes collaboration easier (e.g.: for
pair programming and knowledge sharing).

In this learning session we'll work on a simple TDD example. Through this example we'll find out useful shortcuts, tips,
and tricks.

We'll be writing a DEP file parser. A mock DEP file is in [`src/test/java/resources/sample.dep`](src/test/java/resources/sample.dep). 

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


## Task 1: Write the test...

Create the Java file `DepParserTest.java` file in the test sources directory.

You can navigate to the directory via `Ctrl+Shift+N -> t/j/` and then `Alt+Insert`.






# Useful resources

- [IntelliJ shortcut cheatsheet](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)