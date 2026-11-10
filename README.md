# PAG — Media Recording Model

A small Java learning project that models audio and video recordings. It demonstrates
encapsulation, inheritance, method overriding and object comparison through a simple
console example.

## What it does

The program creates a recording of **Africa by Toto**, stores its metadata, simulates
playback commands and prints a description of the recording.

- **Recording** stores the title, author, duration, file name, extension and size.
- **VideoRecording** extends `Recording` with video dimensions, color depth and the
  number of audio channels.
- **Main** demonstrates creating and configuring a `Recording`, calling `play()`
  and `pause()`, and printing its details.

Playback is simulated with console messages. The project has no graphical interface
or audio/video decoding, and no media files are required to run the example.

## Example output

```text
toto-africa.MP3 is playing
toto-africa.MP3 is paused
com.company.Recording: "Africa" by Toto; length: 295 seconds; file: toto-africa.MP3, weighing 7829213 bytes.
```

## Run locally

Install a Java Development Kit (JDK) with `java` and `javac` available in your terminal.
The source uses Java 7 language/library features; a modern JDK can compile it.
There are no external dependencies or build-tool requirements.

From the repository root, run:

```sh
cd zad1
javac -encoding UTF-8 -d out src/Main.java src/Recording.java src/VideoRecording.java
java -cp out com.company.Main
```

These commands work in Windows CMD, PowerShell and a Unix shell. Compilation creates
class files in `zad1/out/`; the `.gitignore` excludes `*.class` files.

## Project structure

```text
PAG/
├── README.md
└── zad1/
    ├── .gitignore
    ├── src/
    │   ├── Main.java
    │   ├── Recording.java
    │   └── VideoRecording.java
    └── Dokumentacja/
        └── Recording.html
```

All three Java classes belong to the `com.company` package. The `-d out` compiler
option creates the matching package directories automatically.

## Learning topics

- Private fields accessed through getters and setters.
- A specialized class extending a general recording model.
- Overriding `toString()` and `equals()`, and implementing `hashCode()` in the base class.
- Creating objects and invoking their methods from a console entry point.

## Current limitations

This is an introductory exercise. The setters do not validate metadata, and comparing
partially initialized recordings can throw an exception when file fields are null.
`Main` currently demonstrates only the base `Recording` class. There are no automated
tests. The archived Javadoc page for `Recording` references supporting files that are
not included in this repository.

## Background

The source comments date the original exercise to 2021 and credit Krzysztof Piórkowski
and Uladzislau Prusevich. This README describes the existing implementation.
