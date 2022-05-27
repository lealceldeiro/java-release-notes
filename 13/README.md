# [Java 13](https://docs.oracle.com/en/java/javase/13/) [Release Notes Docummentation](https://www.oracle.com/java/technologies/javase/13-relnotes.html)

## [Release Notes](https://www.oracle.com/java/technologies/javase/13-relnote-issues.html)

### New Features and Enhancements

*core-libs/java.nio*

#### Three new methods have been added to `java.nio.file.FileSystems` to make it easier to use file system providers that treat the contents of a file as a file system.

- `newFileSystem(Path)`
- `newFileSystem(Path, Map<String, ?>)`
- `newFileSystem(Path, Map<String, ?>, ClassLoader)`

#### New `java.nio.ByteBuffer` Bulk get/put Methods Transfer Bytes Without Regard to Buffer Position

`java.nio.ByteBuffer` and the other buffer types in `java.nio` now define absolute bulk get and put methods to transfer contiguous sequences of bytes without regard to or effect on the buffer position.

*core-libs/java.time*

#### New Japanese Era Name Reiwa

An instance representing the new Reiwa era has been added to this update. Unlike other eras, there is no public field for this era. It can be obtained by calling `JapaneseEra.of(3)` or `JapaneseEra.valueOf("Reiwa")`. JDK 13 and later will have a new public field to represent this era.

*core-libs/java.util:i18n*

#### Support for Unicode 12.1
