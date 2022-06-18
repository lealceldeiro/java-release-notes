# [Java 13](https://docs.oracle.com/en/java/javase/13/) [Release Notes Documentation](https://www.oracle.com/java/technologies/javase/13-relnotes.html)

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

*hotspot/gc*

#### JEP 351 ZGC Uncommit Unused Memory

#### Added -XXSoftMaxHeapSize Flag

#### ZGC Maximum Heap Size Increased to 16TB

From 4TB to 16TB.

*hotspot/runtime*

#### JEP 350 Dynamic CDS Archiving

*security-libs/java.security*

#### Configurable Read Timeout for CRLs

#### New keytool `-showinfo -tls` Command for Displaying TLS Configuration Information

*security-libs/javax.crypto*

#### Support for MS Cryptography Next Generation (CNG)

*security-libs/javax.crypto:pkcs11*

#### SunPKCS11 Provider Upgraded with Support for PKCS#11 v2.40

*security-libs/javax.net.ssl*

#### Support for X25519 and X448 in TLS

#### Session Resumption without Server-Side State in JSSE

*security-libs/javax.security*

#### Allow SASL Mechanisms to Be Restricted

*security-libs/javax.xml.crypto*

#### New String Constants for Canonical XML 1.1 URIs

#### [xmldsig] Added KeyValueEC_TYPE

*security-libs/org.ietf.jgss*

#### Added a Default Native [GSS-API](https://docs.oracle.com/cd/E19683-01/816-1331/overview-6/index.html) Library on Windows

*security-libs/org.ietf.jgss:krb5*

#### Support for Kerberos Cross-Realm Referrals (RFC 6806)

*tools/javac*

#### JEP 354 Switch Expressions (Preview)

#### JEP 355 Text Blocks (Preview)

*xml/jaxp*

#### New Methods for Creating DOM and SAX Factories with Namespace Support

### Removed Features and Options

*client-libs*

#### Removal of `awt.toolkit` System Property

*core-libs/java.lang*

#### Removal of Runtime Trace Methods

*core-libs/java.net*

#### Pre-JDK 1.4 SocketImpl Implementations No Longer Supported

*hotspot/runtime*

#### Removal of VM option `-XX+AggressiveOpts`

*security-libs*

#### Duplicated RSA Services No Longer Supported by SunJSSE Provider

*security-libs/java.security*

#### Removal of T-Systems Deutsche Telekom Root CA 2 Certificate

#### Removal of Two DocuSign Root CA Certificates

#### Removal of Two Comodo Root CA Certificates

*security-libs/javax.net.ssl*

#### Removal of the Internal `com.sun.net.ssl` Package Only Used for Compatibility with Legacy JSSE 1.0 Applications

#### Removal of Experimental FIPS 140 Compliant Mode from SunJSSE Provider

*tools/javadoc(tool)*

#### Removal of Old Features from javadoc Tool

The following four features have been removed from the *javadoc* tool:

- Support for generating API documentation using HTML 4
- Support for the "old" javadoc API
- Support for generating documentation using HTML frames
- Support for the `--no-module-directories` option

### Deprecated Features and Options

*client-libs*

#### Deprecated and Unsupported Swing Motif Look and Feel on macOS

In the source code, Swing Motif Look and Feel is deprecated with the intent to remove it in a future release.
Use `javax.swing.plaf.metal.MetalLookAndFeel` instead.

*core-libs/java.rmi*

#### Deprecated rmic Tool for Removal

*hotspot/runtime*

#### Deprecated Java Options `-Xverifynone` and `-noverify`

*security-libs/javax.net.ssl*

#### Deprecated `javax.security.cert` APIs with `forRemoval=true`

### Other notes

*client-libs*

#### `GraphicsEnvironment.getCenterPoint()` and `getMaximumWindowBounds()` are Unified Across Platforms

*client-libs/2d*

#### Windows 2019 Core Server Is Not Supported

*core-libs*

#### Improved Handling of the "Class-Path" JAR Manifest Attribute

*core-libs/java.lang*

#### `StringBuffer(CharSequence)` and `StringBuilder(CharSequence)` Throw `NegativeArraySizeException` for Negatively Sized Argument

#### Default Process launch mechanism on Linux now uses posix_spawn

`Runtime.exec()` and `ProcessBuilder`, on Linux now use *posix_spawn(3)* to spawn child processes.
This increases reliability and performance in low-memory situations.

*core-libs/java.lang.invoke*

#### `Lookup.unreflectSetter(Field)` Now Throws `IllegalAccessException` for Static Final Fields

*core-libs/java.net*

#### Change to Default Implementation of `SocketImpl` Methods `supportedOptions`, `getOption`, and `setOption`

#### Change to `ServerSocket.accept()` When the System-Wide Factory for Client or Server Socket Implementations Is Set

#### JEP 353 Reimplement the Legacy Socket API

*core-libs/java.nio*

#### `Files.createSymbolicLink` Can Be Used in "Developer Mode" Without Additional Privileges

#### JNI `NewDirectByteBuffer` Creates Direct Buffer That Is `java.nio.ByteOrder.BIG_ENDIAN`

#### `Files.isHidden` Returns true for Hidden Directories on Windows

*core-libs/java.nio.charsets*

#### Corrected UnicodeDecoder U+FFFE Handling

*core-libs/java.time*

#### `DateTimeFormatter` now throws `DateTimeParseException` on Invalid `HOUR_OF_AMPM`

*core-libs/java.util*

#### Base64.Encoder and Base64.Decoder Methods Can Throw OutOfMemoryError

#### *Properties* Files Containing Malformed Unicode Was Sometimes Misparsed

*core-libs/java.util.jar*

#### Using the ZIP File System (`zipfs`) Provider to Update a ZIP or JAR File Containing Uncompressed Entries Might Corrupt the File

*core-libs/java.util.logging*

#### `NullPointerException` in `java.util.logging.Handler#isLoggable`

*core-libs/java.util:i18n*

#### Upgraded CLDR to Version 35.1

*hotspot/compiler*

#### More Registers Available When Running Without Compressed References on x86_64

*hotspot/gc*

#### Improve Ergonomics for Sparse PRT Entry Size

#### Improvements in Serial GC Young pause time report

#### Improve the Behavior of MaxRAM Settings and UseCompressedOops

The following are the options impacted by this change:

- `-XX:MaxRAMPercentage`
- `-XX:MaxRAMFraction`
- `-XX:MinRAMPercentage`
- `-XX:MinRAMFraction`
- `-XX:InitialRAMPercentage`
- `-XX:InitialRAMFraction`
- `-XX:MaxRAM`

Note: This change only impacts 64-bit platforms.

*security-libs/javax.crypto*

#### Use SunJCE Mac in SecretKeyFactory PBKDF2 Implementation

*security-libs/javax.crypto:pkcs11*

#### Memory Growth Issue in SunPKCS11 Fixed

*security-libs/javax.net.ssl*

#### Updated the Default Enabled Cipher Suites Preference

#### Use Server Cipher Suites Preference by Default

*security-libs/javax.xml.crypto*

#### Updated XML Signature Implementation to Apache Santuario 2.1.3

*tools/javac*

#### Bad EnclosingMethod Attribute on Classes Declared in Lambdas

#### `javac` Rejects Class Files with Broken EnclosingMethod Attribute

*tools/javap*

#### javap Checksum Uses SHA-256
[javap](https://docs.oracle.com/javase/7/docs/technotes/tools/windows/javap.html) includes a checksum of the contents of
the class file in verbose output. The checksum is now calculated with the SHA-256 algorithm, instead of the older MD5
algorithm.

*tools/jlink*

#### A jrt URI Can Only Encode Paths to Files in /modules Tree

*xml/javax.xml.parsers*

#### Change DOM Parser to Not Resolve EntityReference and Add Text Node with DocumentBuilderFactory.setExpandEntityReferences(false)
