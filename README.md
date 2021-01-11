## Sample JavaFX Gradle Application [![JetBrains team project](http://jb.gg/badges/team.svg)](https://confluence.jetbrains.com/display/ALL/JetBrains+on+GitHub)

A simple JavaFX application based off the [OpenJFX getting started documentation](https://openjfx.io/openjfx-docs/) that uses Gradle as the build system.

The project was created using the standard IntelliJ IDEA project wizard for creating Gradle projects.

This is a modular application, i.e. it uses Java Modules (Java 9 modularity / Jigsaw). There's a bit of finessing to do on the Gradle side to support this, specifically I can't use the [JavaFX Gradle plugin](https://github.com/openjfx/javafx-gradle-plugin) as there's a [known issue using this with a version of Gradle higher than 6.5](https://github.com/openjfx/javafx-gradle-plugin/issues/89) (this project uses Gradle 6.8). I combined the workaround detailed in that ticket with [this StackOverflow answer](https://stackoverflow.com/a/65209664/653519) to create a Gradle build file that works with JavaFX, Java 15 and modules.

It might be easier with Gradle projects to not use modularity, but if we do then the application runs exactly as you'd expect from the command line:

    ./gradlew clean run

and by running the application class itself in IntelliJ IDEA. It also works as expected from the Gradle tool window.

This seems to be the best approach to take to get a JavaFX application working with Gradle and IntelliJ IDEA.