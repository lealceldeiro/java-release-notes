# [Java 12](https://docs.oracle.com/en/java/javase/12/) [Release Notes Docummentation](https://www.oracle.com/java/technologies/javase/12-relnotes.html)

## [Release Notes](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html)

## What's New in JDK 12 - New Features and Enhancements

*core-libs/java.lang*

[Support for Unicode 11](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8209923)

[POSIX_SPAWN Option on Linux](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8212828)

*core-libs/java.lang.invoke*

[JEP 334 JVM Constants API](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8203252)

*core-libs/java.text*

[Support for Compact Number Formatting](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8177552). i.e.:

```java
NumberFormat fmt = NumberFormat.getCompactNumberInstance(Locale.US, NumberFormat.Style.SHORT);
String result = fmt.format(1000);  // 1K
```
