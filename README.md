# IntelliJ Learning Session

We'll be working with IntelliJ's default shortcuts.

Case for using defaults: it makes collaboration easier (e.g.: pair programming and knowledge sharing).

In this learning session we'll work on a simple TDD example. Through this example we'll find out useful shortcuts, tips,
and tricks.

We'll be writing a DEP file parser. A mock DEP file is in [`src/test/java/resources/sample.dep`](src/test/java/resources/sample.dep).

We'll try to avoid using the mouse as much as possible (unfortunately sometimes we'll still need it). 

Let's get started.

## Getting started

1. Clone this project (open `Start -> git bash`):

    ```bash
    git clone https://github.com/mupdt982/gradle-hello-world.git
    ```

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


Note: `Shift Shift` gives too many results. Try using specialized shortcuts like `Ctrl+Shift+A` to find actions,
`Ctrl+Shift+N` to find files, `Ctrl+N` to find classes, `Ctrl+Alt+Shift+N` to find symbols in code.


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

- open file in the editor from the project tab (or other contexts) `F4` and find the file in project tab with `Alt+F1`,

- resize tabs with `Ctrl+Shift+Left|Right`

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

Write the test using the live template. Use the `assertEquals` static function. We will write 
the test for the `getName` method on the parsed Dep file.

We will use:

- `Ctrl+Space Space` to bring up all static methods,

- Then we will use `Alt+Enter` to import it statically,

- `Ctrl+F6` to change the signature of the `fromString` function,

- We will use the "Problems" tab to fix the problems introduced by the signature change and navigate between the
    problems with `Ctrl+Alt+Up|Down`,

- `Alt+4` to open the running tests,

- run all tests not just the specific one,

- Use `Ctrl+Alt+T` to surround the exception with `if`,

- Use `Ctrl+Shit+T` to go to  or generate tests.


## Generate tests for `DepFile`

Use `Ctrl+Shift+T` to automatically generate tests.

We should also:
 
- override the `toString` function on `DepFile` (with `Ctrl+O`),

- generate other sorts of things with `Alt+Insert` (which is btw a generic "add a thing to context" shortcut useful
    elsewhere in IntelliJ).


## Time to commit changes

We will inspect the changes we made with the help of `Alt+9`. In the history tab, you can navigate between
local changes and the log with `Alt+Left|Right`.

With the help of `Alt+Backtick` we can explore Git history as well as local history (the latter is maintained by
IntelliJ and is much more fine-grained).

We will commit changes with IntelliJ's VCS support.

- Press `Ctrl+K`.

- If you have multiple modules in your projects each of them with its own VCS root, you can 
    commit them together or separately. 

Clipboard:

- clipboard from history: `Ctrl+Shift+V`

- Pro tip: set the clipboard history to much more than the default (`Ctrl+Shift+A max clipb`).

- never forget "compare with clipboard".

Resolving conflicts:

- reproduce a merge conflict,

- in IntelliJ do `Ctrl+Shift+A resolve conflicts`,

- use `F7` to navigate between changes.


## Awesome editor magic

- Duplication: `Ctrl+D`

- Multi-cursor editing:

    - multi-select words or selection: `Alt+J`,
    
    - multi-selection with the mouse: `Alt+Shift & mouse clicks...`,
    
    - toggle block selection: `Alt+Shift+Insert`

- Line manipulation:

    - Join lines: `Ctrl+Shift+J`

- Surround with parentheses (get to the setting with `Ctrl+Shift+A surround selection brace`).

- Raw copy (that doesn't apply formatting) with `Ctrl+Alt+Shift+V`.


## Remote debugging

1.  Run your process on a remote host:
    
    ```bash
    /opt/java/jdk1.8.0_131/bin/java -agentlib:jdwp=transport=dt_socket,server=y,suspend=n,address=5005 -jar idea-tdd-example-1.0-SNAPSHOT.jar
    ```

1. Create a remote debug run configuration by pressing `Alt+Shift+F10 -> 0 (Edit Configurations...) -> Alt+Insert -> "Remote`.

1. Happy debugging!


## Persisting your IntelliJ configuration

Simple, put `~/.IntelliJIdea2017.2/config/` into git.

You can also export/import settings.

## Shared team settings

Why? Because you probably want to standardize on the code style.

Try this out: https://www.jetbrains.com/help/phpstorm/sharing-your-ide-settings.html

Disclaimer: I haven't used this plugin. Instead I committed the settings into the project's git repo (which is not a good idea).


# Useful resources

- [IntelliJ shortcut cheatsheet](https://resources.jetbrains.com/storage/products/intellij-idea/docs/IntelliJIDEA_ReferenceCard.pdf)