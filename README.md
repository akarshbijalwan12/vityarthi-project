# Riddle Game

A simple command-line riddle game written in Java. The program picks a random
riddle, lets the player type an answer, offers an optional hint on a wrong
answer, and keeps score across as many rounds as the player wants to play.

## Project Structure

## Prerequisites

You need a Java Development Kit (JDK) installed — version 8 or later is
enough (any modern version, e.g. JDK 11, 17, or 21, works fine). This project
has no external dependencies (no Maven/Gradle build file is required), so a
plain JDK installation is all you need.

To check whether Java is already installed, open a terminal and run:

```bash
java -version
javac -version
```

If both commands print a version number, you're ready to go. If not, install
a JDK first:

- **Windows / macOS / Linux:** Download and install a JDK from
  [Adoptium (Eclipse Temurin)](https://adoptium.net/) or
  [Oracle JDK](https://www.oracle.com/java/technologies/downloads/), then
  make sure `java` and `javac` are on your system `PATH`.
- **macOS (Homebrew):** `brew install openjdk`
- **Ubuntu/Debian:** `sudo apt update && sudo apt install default-jdk`

## Setup

1. **Get the code.** Clone this repository (or download and extract it):

```bash
   git clone <this-repository-url>
   cd riddle-game
```

2. **No dependency installation is required.** The game only uses the Java
   standard library (`java.util.Scanner`), so there are no external packages
   to install and no configuration files to edit.

## Compiling the Project

From the root of the repository, compile the source file. This example
outputs the compiled `.class` file into a `bin/` folder to keep the project
tidy:

```bash
javac -d bin src/RiddleGame.java
```

This creates `bin/RiddleGame.class`.

## Running the Project

Run the compiled program with:

```bash
java -cp bin RiddleGame
```

You should see a riddle printed to the console, for example:

Type your answer and press **Enter**. The game will:

- Print `Correct!` and increase your score if you're right.
- Print `Wrong!` and ask `Would you like a hint? (yes/no)` if you're wrong.
  Type `yes` to see a hint, or `no` (or anything else) to skip it.

After each round, you'll be asked:

Type `yes` to get another random riddle, or anything else to stop. When you
stop, your final score is printed and the program exits.

### Example Session

## Notes

- Answers are checked case-insensitively (e.g. `an echo`, `An Echo`, and
  `AN ECHO` are all accepted), but must match the expected answer text
  exactly otherwise (e.g. just `echo` without `An` will **not** be accepted).
- Riddles are chosen at random each round, so you may see the same riddle
  more than once in a session.
- The game runs indefinitely until you choose not to continue, so always
  answer the "Continue playing?" prompt with something other than `yes` when
  you want to stop.

## Troubleshooting

| Problem | Likely Cause | Fix |
|---|---|---|
| `javac: command not found` | JDK not installed or not on `PATH` | Install a JDK and ensure its `bin` folder is in your `PATH` |
| `Error: Could not find or load main class RiddleGame` | Running `java` from the wrong directory, or wrong classpath | Make sure you run `java -cp bin RiddleGame` from the repository root, after compiling with `javac -d bin src/RiddleGame.java` |
| Program exits immediately / skips input prompts | Extra blank lines or trailing spaces piped into input | Make sure you press Enter after typing each answer, with no leading/trailing spaces |
