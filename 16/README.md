# [Java 16](https://docs.oracle.com/en/java/javase/16/) [Release Notes Documentation](https://www.oracle.com/java/technologies/javase/16-relnotes.html)

## [Release Notes](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html)

### New Features and Enhancements

*core-libs*

#### [JEP 389: Foreign Linker API (Incubator)](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8249755)

#### [JEP 396: Strongly Encapsulate JDK Internals by Default](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8256299)

#### [JEP 393: Foreign-Memory Access API (Third Incubator)](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8253415)

#### [JEP 390: Warnings for Value-based Classes](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8249100)

*core-libs/java.lang:reflect*

#### [Add InvocationHandler::invokeDefault Method for Proxy's Default Method Support](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8159746)

*core-libs/java.nio*

#### [JEP 380: Unix domain sockets](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8238588)

*core-libs/java.time*

#### [Day Period Support Added to `java.time` Formats](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8247781)

A new formatter pattern, letter 'B', and its supporting method have been added to
`java.time.format.DateTimeFormatter`/`DateTimeFormatterBuilder` classes. Example:

```shell
DateTimeFormatter.ofPattern("yyyy-MM-dd hh:mm B")
                 .format(LocalDateTime.of(2022, 6, 21, 17, 42)); // "2022-06-21 05:42 in the afternoon"
```

*core-libs/java.util.stream*

#### [Add `Stream.toList()` Method](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8180352)

*hotspot/compiler*

#### [JEP 338: Vector API (Incubator)](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8201271)

#### [Improved CompileCommand Flag](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8256508)

*hotspot/gc*

#### [JEP 376: ZGC Concurrent Stack Processing](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8239600)

#### [Concurrently Uncommit Memory in G1](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8236926)

*hotspot/jfr*

#### [New jdk.ObjectAllocationSample Event Enabled by Default](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8257602)

*hotspot/runtime*

#### [JEP 387: Elastic Metaspace](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8251158)

*security-libs/java.security*

#### [Signed JAR Support for RSASSA-PSS and EdDSA](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8242068)

#### [SUN, SunRsaSign, and SunEC Providers Supports SHA-3 Based Signature Algorithms](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8172366)

#### [jarsigner Preserves POSIX File Permission and symlink Attributes](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8218021)

#### [Added `-trustcacerts` and `-keystore` Options to `keytool -printcert` and `-printcrl` Commands](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8244148)

*security-libs/javax.crypto*

#### [SunPKCS11 Provider Supports SHA-3 Related Algorithms](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8242332)

*security-libs/javax.net.ssl*

#### [Improve Certificate Chain Handling](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8245417)

#### [Improve Encoding of TLS Application-Layer Protocol Negotiation (ALPN) Values](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8254631)

#### [TLS Support for the EdDSA Signature Algorithm](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8166596)

*tools/javac*

#### [JEP 397: Sealed Classes (Second Preview)](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8246775)

#### [JEP 395: Records](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8246771)

#### [JEP 394: Pattern Matching for `instanceof`](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8250623)

*tools/jpackage*

#### [JEP 392: Packaging Tool](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8247768)

### Removed Features and Options

*client-libs/java.awt*

#### [Removal of java.awt.PeerFixer](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8253965)

*hotspot/compiler*

#### [Removal of Experimental Features AOT and Graal JIT](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8255616)

*hotspot/runtime*

#### [Deprecated Tracing Flags Are Obsolete and Must Be Replaced With Unified Logging Equivalents](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8256718)

| Obsoleted Option           | Unified Logging Replacement |
|----------------------------|-----------------------------|
| `-XX:+TraceClassLoading`   | `-Xlog:class+load=info`     |
| `-XX:+TraceClassUnloading` | `-Xlog:class+unload=info`   |
| `-XX:+TraceExceptions`     | `-Xlog:exceptions=info`     |

*security-libs/java.security*

#### [Removed Root Certificates with 1024-bit Keys](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8243559)

*security-libs/javax.crypto*

#### [Removal of Legacy Elliptic Curves](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8235710)

### Deprecated Features and Options

*core-libs/java.lang*

#### [Terminally Deprecated ThreadGroup stop, destroy, isDestroyed, setDaemon and isDaemon](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8256643)

*hotspot/runtime*

#### [Parts of the Signal-Chaining API Are Deprecated](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8257572)

*security-libs/java.security*

#### [Deprecated the `java.security.cert` APIs That Represent DNs as Principal or String Objects](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8241003)

### Other notes

*core-libs/java.io*

#### [Line Terminator Definition Changed in java.io.LineNumberReader](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8235792)

*core-libs/java.io:serialization*

#### [Enhanced Support of Proxy Class](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8236862)

*core-libs/java.lang*

#### [Support Supplementary Characters in String Case Insensitive Operations](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8248655)

For example, `"\ud801\udc00".equalsIgnoreCase("\ud801\udc28")` returns `true`,

because `'𐐀'` (`"\ud801\udc00"`) and
`'𐐨'` (`"\ud801\udc28"`) are equal to each other character in case-insensitive comparison.

#### [Module::getPackages Returns the Set of Package Names in This Module](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8256063)

*core-libs/java.lang:reflect*

#### [Proxy Classes Are Not Open for Reflective Access](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8159746)

*core-libs/java.net*

#### [The Default `HttpClient` Implementation Returns Cancelable Futures](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8245462)

#### [`HttpClient.newHttpClient` and `HttpClient.Builder.build` Might Throw `UncheckedIOException`](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8248006)

#### [HttpPrincipal::getName Returned Incorrect Name](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8255584)

The behavior of the `HttpPrincipal::getName` method has been updated to return the name in the correct format as
outlined in its specification, i.e. `"realm:username"`. Previously, the method incorrectly returned `"username"` only.

*core-libs/java.nio*

#### [Incomplete Support for Unix Domain Sockets in Windows 2019 Server](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8259014)

#### [(fs) NullPointerException Not Thrown When First Argument to Path.of or Paths.get Is null](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8254876)

#### [DataInputStream:readFully now correctly throws specified exceptions](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8245036)

*core-libs/java.time*

#### [US/Pacific-New Zone Name Removed as Part of tzdata2020b](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8254177)

Information regarding this update can be viewed at Information regarding this update can be viewed at
[https://mm.icann.org/pipermail/tz-announce/2020-October/000059.html](https://mm.icann.org/pipermail/tz-announce/2020-October/000059.html)

*core-libs/java.util*

#### [Argument Index of Zero or Unrepresentable by int Throws IllegalFormatException](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8253459)

*core-libs/java.util.jar*

#### [Refine ZipOutputStream.putNextEntry() to Recalculate ZipEntry's Compressed Size](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8253952)

#### [GZIPOutputStream Sets the GZIP OS Header Field to the Correct Default Value](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8244706)

*core-libs/java.util.logging*

#### [`java.util.logging.LogRecord` Updated to Support Long Thread IDs](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8245302)

*core-libs/java.util:collections*
#### [TreeMap.computeIfAbsent Mishandles Existing Entries Whose Values Are null](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8259622)

*core-libs/java.util:i18n*

#### [Support for CLDR Version 38](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8251317)

*core-libs/javax.naming*

#### [Added Property to Control LDAP Authentication Mechanisms Allowed to Authenticate Over Clear Connections](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8237990)

#### [LDAP Channel Binding Support for Java GSS/Kerberos](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8245527)

*hotspot/gc*

#### [Shenandoah: Concurrent weak reference processing](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8254315)

*hotspot/jvmti*

#### [Make JVMTI Table Concurrent](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8212879)

*hotspot/runtime*

#### [IncompatibleClassChangeError Exceptions Are Thrown For Failing 'final' Checks When Defining a Class](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8243583)

#### [Object Monitors No Longer Keep Strong References to Their Associated Object](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8247281)

*security-libs/java.security*

#### [Added Entrust Root Certification Authority - G4 certificate](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8243321)

#### [Added 3 SSL Corporation Root CA Certificates](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8243320)

#### [Upgraded the Default PKCS12 Encryption and MAC Algorithms](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8153005)

*security-libs/javax.net.ssl*

#### [Disable TLS 1.0 and 1.1](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8202343)

*tools/javac*

#### [Annotation Interfaces May Not Be Declared As Local Interfaces](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8250741)

#### [C-Style Array Declarations Are Not Allowed in Record Components](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8250629)

#### [DocLint Support Moved to jdk.javadoc Module](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8252712)

*tools/javadoc(tool)*

#### [Improvements for JavaDoc Search](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8244535)

#### [API Documentation Links to Platform Documentation](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8216497)

#### [Viewing API Documentation on Small Devices](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8248566)

#### [Eliminating Duplication in Simple Documentation Comments](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8075778)

#### ["Type" Terminology in Generated Documentation](https://www.oracle.com/java/technologies/javase/16-relnote-issues.html#JDK-8258002)
