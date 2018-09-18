Marian's Java Bill Of Materials [![Build Status](https://travis-ci.org/zaplatynski/java-bom.svg?branch=master)](https://travis-ci.org/zaplatynski/java-bom)
================================

This is a bill of materials (BOM) suitable for most OpenSource Java projects as Maven parent pom.

It configures:
* The Maven Java compiler plugin to a *certain version*, e.g. 8 (1.8)
* Takes care that all dependencies have *maximum byte code compatible transitive dependencies of certain version* e.g. 8 (1.8)
* Checks that all *transitive dependencies resolves to common version* and forces the developer to declare it e.g. inside the dependency management.
* Adds the *Maven information* such as name and ids such as artifact id and group id to the Java's *jar manifest file*
* Creates additional jar files for *source* and *JavaDoc* as required by Maven Central for easy access of the source code by IDEs such as Eclipse or IDEA
* Provides *JUnit 5* as unit test engine with support for *JUnit 3* and *JUnit 4* tests so that all unit tests of JUnit 3, 4 and 5 can run at the same time
* Adds *Mockito, *AssertJ* and *Hamcrest* support for unit tests

How to add to your Maven project
--------------------------------

Just reference the BOM as the parent POM in your project's pom.xml:

```xml
<project>
	
	<parent>
		<groupId>com.github.zaplatynski</groupId>
		<artifactId>java-bom</artifactId>
		<version>1.1.1</version>
	</parent>
	
	...
	
</project>
```

How to modify a version such as the Java version
------------------------------------------------

All versions are stored inside properties for easy adaption e.g. use Java 7 instead of 8:

```xml
<project>
	
	<parent>
		<groupId>com.github.zaplatynski</groupId>
		<artifactId>java-bom</artifactId>
		<version>1.1.1</version>
	</parent>
	
	...
	
	<properties>
		<java.version>1.7<version>
	</properties>
	
	...
	
</project>
```
