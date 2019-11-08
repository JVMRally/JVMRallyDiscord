# Summary of talks in Devoxx 2019

 - [Why we hate Java serialization and what we might do about it by Brian Goetz & Stuart Marks [50 minutes]](#Why-we-hate-Java-serialization-and-what-we-might-do-about-it)
 - [Ask the Java architects [50 minutes]](#Ask-the-Java-architects)
 - [Building your own JDK in 10 steps [30 minutes]](#Building-your-own-jdk-in-10-steps)
 - [Java keeps throttling up [2 hours 30 minutes]](#Java-keeps-throttling-up)

## Why we hate Java serialization and what we might do about it

https://www.youtube.com/watch?v=dOgfWXw9VrI

### Speakers
 - Brian Goetz [@briangoetz](https://twitter.com/BrianGoetz)
 - Stuart Marks [@stuartmarks](https://twitter.com/stuartmarks)
 
### Summary

A look at why current serialization can be problematic and dangerous, and some of the current thoughts of how these problems could be solved with future JDK updates.

 - [I use DTOs to transfer data between layers to avoid the problems of serialization, why should I use serialization?](https://youtu.be/dOgfWXw9VrI?t=2909)
 - [Aren't you comprimising your principles?](https://youtu.be/dOgfWXw9VrI?t=3042)

## Ask the Java architects

https://www.youtube.com/watch?v=qKeMB7OoGJk

### Speakers
 - Brian Goetz [@briangoetz](https://twitter.com/BrianGoetz)
 - Stuart Marks [@stuartmarks](https://twitter.com/stuartmarks)
 - Ron Pressler [@pressron](https://twitter.com/pressron)
 
### Summary
A Q&A session with Java architects. The questions below are linked to the appropriate timestamp in the video.

 - [Is there a relationship between serialization and value types in project valhalla?](https://youtu.be/qKeMB7OoGJk?t=102)
 - [How does that work with a value type inlined with another class](https://youtu.be/qKeMB7OoGJk?t=210)
 - [What's the status of project portola?](https://youtu.be/qKeMB7OoGJk?t=254)
 - [Can we reasonably get rid of checked exceptions?](https://youtu.be/qKeMB7OoGJk?t=305)
 - [What's next to be deprecated?](https://youtu.be/qKeMB7OoGJk?t=490)
 - [Why are textblocks being previewed again [in java 14]?](https://youtu.be/qKeMB7OoGJk?t=695)
 - [What advantage does project loom bring and how will the programming model change?](https://youtu.be/qKeMB7OoGJk?t=1065)
 - [Will graal replace the standard JVM?](https://youtu.be/qKeMB7OoGJk?t=1410)
 - [When are we going to get data classes [records] in java?](https://youtu.be/qKeMB7OoGJk?t=1550)
 - [What changes have been introduced with switch expressions for java 14?](https://youtu.be/qKeMB7OoGJk?t=1620)
 - [Numeric promotion in ternary expressions and switch expressions](https://youtu.be/qKeMB7OoGJk?t=1650)
 - [Why are the unmodifable collection initialisers (`Map.of`, `List.of`) limited to 10 arguments?](https://youtu.be/qKeMB7OoGJk?t=1730)
 - [Will we get extension methods?](https://youtu.be/qKeMB7OoGJk?t=1855)
 - [Will you bring co-rountines java from kotlin?](https://youtu.be/qKeMB7OoGJk?t=1990)
 - [Will you bring the pipeline operator?](https://youtu.be/qKeMB7OoGJk?t=2025)
 - [Are there plans for a new reflections API?](https://youtu.be/qKeMB7OoGJk?t=2150)
 - [What is the status of project panama?](https://youtu.be/qKeMB7OoGJk?t=2325)
 - [What are your thoughts on how widely the module system has been adopted?](https://youtu.be/qKeMB7OoGJk?t=2560)
 - [What's the next big thing for java after valhalla, loom, and panama?](https://youtu.be/qKeMB7OoGJk?t=2925)

## Building your own JDK in 10 steps

https://www.youtube.com/watch?v=lhkjOrY65Ts

### Speakers
 - Jose Paumard [@JosePaumard](https://twitter.com/JosePaumard)
 
### Summary
 
 - [Why build your own JDK?](https://youtu.be/lhkjOrY65Ts?t=37)
 - [Are you really building a JDK?](https://youtu.be/lhkjOrY65Ts?t=458)
 - [Starting point](https://youtu.be/lhkjOrY65Ts?t=510)
 
#### Steps

1. `sudo apt-get install mercurial`
2. Choose a branch
3. `hg clone http://hg.openjdk.java.net/loom/loom` (The repositories are roughly 2.5GB)
4. `hg branches`
5. Check the branches are up to date
    - `hg pull` to update
6. `hg branchname` to switch to the branch
7. Install `autoconf`, `make`, `build-essential`, X11 libraries, `libcups2-dev`, and `libasound2`
    - `sudo apt-get install autoconf`
    - `sudo apt-get install make`
    - `sudo apt-get install build-essential`
    - `sudo apt-get install libx11-dev libxext-dev libxrender-dev libxrandr-dev libxtst-dev libxt-dev`
    - `sudo apt-get install libcups2-dev`
    - `sudo apt-get install libasound2-dev`
8. Run `./configure`
9. Run `make images` (Can take > 20 minutes, and you'll need 6-7GB of space)
10. The result is in `server-release/images/jdk`
11. Now you can use the JDK in the same way as any other JDK. To compile and test new features you may need to use `-enable-preview` and `-source 14` during compilation and execution.

 - [Demonstration of some amber features](https://youtu.be/lhkjOrY65Ts?t=1290)

## Java keeps throttling up

### Speakers

 - Jose Paumard [@JosePaumard](https://twitter.com/JosePaumard)
 - Remi forax [forax](https://github.com/forax)
 
### Summary

A deep dive into some of the new features coming to java in the near future.

 - [Looking at the past](https://youtu.be/Y-744emVGoo?t=144)
 - [Demo of new NPE message](https://youtu.be/Y-744emVGoo?t=490)
 - [Loom - Erlang's actors](https://youtu.be/Y-744emVGoo?t=811)
 - [Amber - Haskel's pattern matching](https://youtu.be/Y-744emVGoo?t=2636)
 - [Valhalla - Kotlin's sealed type + data class](https://youtu.be/Y-744emVGoo?t=3734)
 - [Panama - Groovy's smart cast](https://youtu.be/Y-744emVGoo?t=5275)