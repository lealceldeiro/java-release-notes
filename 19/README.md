# [Java 19](https://docs.oracle.com/en/java/javase/19/)

## [Consolidated Release Notes](https://www.oracle.com/java/technologies/javase/19all-relnotes.html)

### Major New Functionality

#### 1. Concurrency Model Update Previews

[JEP 425](https://bugs.openjdk.org/browse/JDK-8277131) Virtual Threads (Preview)

Introduce virtual threads to the Java Platform. Virtual threads are lightweight threads that dramatically reduce the
effort of writing, maintaining, and observing high-throughput concurrent applications.
[This is a preview API](https://openjdk.org/jeps/11).

[JEP 428](https://bugs.openjdk.org/browse/JDK-8277129) Structured Concurrency (Incubator)

Simplify multithreaded programming by introducing an API for structured concurrency. Structured concurrency treats
multiple tasks running in different threads as a single unit of work, thereby streamlining error handling and
cancellation, improving reliability, and enhancing observability.
[This is an incubating API](https://openjdk.java.net/jeps/12).

#### 2. Language Feature Previews

[JEP 405](https://bugs.openjdk.org/browse/JDK-8260244) Record Patterns (Preview)

Enhance the Java programming language with record patterns to deconstruct record values. Record patterns and type
patterns can be nested to enable a powerful, declarative, and composable form of data navigation and processing. This
is a preview language feature.

[JEP 427](https://bugs.openjdk.org/browse/JDK-8282272) Pattern Matching for switch (Third Preview)

Enhance the Java programming language with pattern matching for switch expressions and statements. Extending pattern
matching to switch allows an expression to be tested against a number of patterns, each with a specific action, so that
complex data-oriented queries can be expressed concisely and safely. This is a preview language feature.

#### 3. Libraries Preview/Incubator

[JEP 424](https://bugs.openjdk.org/browse/JDK-8282048) Foreign Function & Memory API (Preview)

Introduce an API by which Java programs can interoperate with code and data outside of the Java runtime. By efficiently
invoking foreign functions (i.e., code outside the JVM), and by safely accessing foreign memory (i.e., memory not
managed by the JVM), the API enables Java programs to call native libraries and process native data without the
brittleness and danger of JNI. [This is a preview API](https://openjdk.java.net/jeps/12).

[JEP 426](https://bugs.openjdk.org/browse/JDK-8280173) Vector API (Fourth Incubator)

Introduce an API to express vector computations that reliably compile at runtime to optimal vector instructions on
supported CPU architectures, thus achieving performance superior to equivalent scalar computations.

### New Features

*core-libs/java.lang*

[Support Unicode 14.0](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8268081)
([JDK-8268081](https://bugs.openjdk.org/browse/JDK-8268081))

[New system properties for `System.out` and `System.err`](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8283620)
([JDK-8283620](https://bugs.openjdk.org/browse/JDK-8283620))

- `stdout.encoding`
- `stderr.encoding`

*core-libs/java.net*

[HTTPS Channel Binding Support for Java GSS/Kerberos](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8279842)
([JDK-8279842](https://bugs.openjdk.org/browse/JDK-8279842))

*core-libs/java.time*

[Additional Date-Time Formats](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8176706)
([JDK-8176706](https://bugs.openjdk.org/browse/JDK-8279842))

*core-libs/java.util:collections*

[New Methods to Create Preallocated HashMaps and HashSets](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8186958)
([JDK-8186958](https://bugs.openjdk.org/browse/JDK-8186958))

_hotspot/compiler_

[Support for PAC-RET Protection on Linux/AArch64](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8277204)
([JDK-8277204](https://bugs.openjdk.org/browse/JDK-8277204))

_hotspot/runtime_

[Automatic Generation of the CDS Archive](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8261455)
([JDK-8261455](https://bugs.openjdk.org/browse/JDK-8261455))

_security-libs/java.security_

[Windows KeyStore Updated to Include Access to the Local Machine Location](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-6782021)
([JDK-6782021](https://bugs.openjdk.org/browse/JDK-6782021))

[Break Up SEQUENCE in X509Certificate::getSubjectAlternativeNames and X509Certificate::getIssuerAlternativeNames in
otherName](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8277976)
([JDK-8277976](https://bugs.openjdk.org/browse/JDK-8277976))

_security-libs/javax.net.ssl_

[(D)TLS Signature Schemes](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8280494)
([JDK-8280494](https://bugs.openjdk.org/browse/JDK-8280494))

_security-libs/jdk.security_

[Add a -providerPath Option to jarsigner](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8281175)
([JDK-8281175](https://bugs.openjdk.org/browse/JDK-8281175))

_security-libs/org.ietf.jgss:krb5_

[New Options for ktab to Provide Non-default Salt](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8279064)
([JDK-8279064](https://bugs.openjdk.org/browse/JDK-8279064))

_xml/jaxp_

[New XML Processing Limits](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8270504)
(JDK-8270504 (not public))

### Removed Features and Options

_hotspot/gc_

[Removal of Diagnostic Flag GCParallelVerificationEnabled](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8286304)
([JDK-8286304](https://bugs.openjdk.org/browse/JDK-8286304))

_security-libs/javax.net.ssl_

[Remove Finalizer Implementation in SSLSocketImpl](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8212136)
([JDK-8212136](https://bugs.openjdk.org/browse/JDK-8212136))

_security-libs/javax.security_

[Remove the Alternate ThreadLocal Implementation of the Subject::current and Subject::callAs APIs](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8282676)
(JDK-8282676 (not public))

### Deprecated Features and Options

_core-libs/java.lang_

[java.lang.ThreadGroup Is Degraded](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284161)
([JDK-8284161](https://bugs.openjdk.org/browse/JDK-8284161))

_core-libs/java.util:i18n_

[Deprecation of Locale Class Constructors](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8282819)
([JDK-8282819](https://bugs.openjdk.org/browse/JDK-8282819))

_security-libs/java.security_

[PSSParameterSpec(int) Constructor and DEFAULT Static Constant Are Deprecated](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8254935)
([JDK-8254935](https://bugs.openjdk.org/browse/JDK-8254935))

_security-libs/javax.crypto_

[OAEPParameterSpec.DEFAULT Static Constant Is Deprecated](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284553)
([JDK-8284553](https://bugs.openjdk.org/browse/JDK-8284553))

### Other Notes

_client-libs/2d_

[Metal Is Now the Default Java 2D Rendering Pipeline on macOS](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284378)
([JDK-8284378](https://bugs.openjdk.org/browse/JDK-8284378))

_core-libs/java.io_

[New System Property to Disable Windows Alternate Data Stream Support in java.io.File](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8285445)
([JDK-8285445](https://bugs.openjdk.org/browse/JDK-8285445))

_core-libs/java.lang_

[User's Home Directory Is Set to $HOME if Invalid](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8280357)
([JDK-8280357](https://bugs.openjdk.org/browse/JDK-8280357))

[Thread Context ClassLoader Changed to be a Special Inheritable Thread-local](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284161)
([JDK-8284161](https://bugs.openjdk.org/browse/JDK-8284161))

[Source and Binary Incompatible Changes to java.lang.Thread](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284161)
([JDK-8284161](https://bugs.openjdk.org/browse/JDK-8284161))

[Incorrect Handling of Quoted Arguments in ProcessBuilder](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8282008)
([JDK-8282008](https://bugs.openjdk.org/browse/JDK-8282008))

[Double.toString(double) and Float.toString(float) May Return Slightly Different Results](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-4511638)
([JDK-4511638](https://bugs.openjdk.org/browse/JDK-4511638))

_core-libs/java.lang:reflect_

[Make Annotation toString Output for Enum Constants Usable for Source Input](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8281462)
([JDK-8281462](https://bugs.openjdk.org/browse/JDK-8281462))

_core-libs/java.net_

[MD5 and SHA-1 Are Disabled by Default for HTTP Digest Authentication](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8281561)
([JDK-8281561](https://bugs.openjdk.org/browse/JDK-8281561))

[Improved HTTP Proxy Detection on Windows](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8262442)
([JDK-8262442](https://bugs.openjdk.org/browse/JDK-8262442))

[java.net.InetAddress Updated to Reject Ambiguous IPv4 Address Literals](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8277608)
(JDK-8277608 (not public))

[Make HttpURLConnection Default Keep Alive Timeout Configurable](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8278067)
([JDK-8278067](https://bugs.openjdk.org/browse/JDK-8278067))

_core-libs/java.nio_

[FileChannel.transferFrom May Transfer Fewer Bytes than Expected](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8286763)
([JDK-8286763](https://bugs.openjdk.org/browse/JDK-8286763))

[The mark and set Methods of InputStream and FilterInputStream Are No Longer Synchronized](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284930)
([JDK-8284930](https://bugs.openjdk.org/browse/JDK-8284930))

[Files.copy Copies POSIX Attributes to Target on Foreign File System](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8267820)
([JDK-8267820](https://bugs.openjdk.org/browse/JDK-8267820))

[FileChannel.lock/tryLock Changed to Treat Size 0 to Mean the Locked Region Goes to End of File](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-5041655)
([JDK-5041655](https://bugs.openjdk.org/browse/JDK-5041655))

_core-libs/java.time_

[Support for IsoFields in JapaneseDate/MinguoDate/ThaiBuddhistDate](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8279185)
([JDK-8279185](https://bugs.openjdk.org/browse/JDK-8279185))

_core-libs/java.util.concurrent_

[ForkJoinPool and ThreadPoolExecutor Do Not Use Thread::start to Start Worker Threads](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284161)
([JDK-8284161](https://bugs.openjdk.org/browse/JDK-8284161))

_core-libs/java.util.jar_

[InflaterInputStream.read Throws EOFException](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8292327)
([JDK-8292327](https://bugs.openjdk.org/browse/JDK-8292327))

_core-libs/java.util.regex_

[Regex \b Character Class Now Matches ASCII Characters only by Default](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8264160)
([JDK-8264160](https://bugs.openjdk.org/browse/JDK-8264160))

_core-libs/java.util:i18n_

[Support for CLDR Version 41](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8265315)
([JDK-8265315](https://bugs.openjdk.org/browse/JDK-8265315))

_core-libs/javax.naming_

[Parsing of URL Strings in Built-in JNDI Providers Is Stricter](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8278972)
(JDK-8278972 (not public))

_core-svc/tools_

[jstatd No Longer Requires a SecurityManager](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8272317)
([JDK-8272317](https://bugs.openjdk.org/browse/JDK-8272317))

_hotspot/jvmti_

[JVM TI Changes to Support Virtual Threads](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8284161)
([JDK-8284161](https://bugs.openjdk.org/browse/JDK-8284161))

_hotspot/runtime_

[JNI GetVersion Returns JNI_VERSION_19](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8286176)
([JDK-8286176](https://bugs.openjdk.org/browse/JDK-8286176))

_hotspot/runtime_

[CPU Shares Ignored When Computing Active Processor Count](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8281181)
([JDK-8281181](https://bugs.openjdk.org/browse/JDK-8281181))

_install/install_

[RPM JDK Installer Changes](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8275446)
([JDK-8275446](https://bugs.openjdk.org/browse/JDK-8275446))

[All JDK Update Releases Are Installed into the Same Directory on macOS](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8281010)
([JDK-8281010](https://bugs.openjdk.org/browse/JDK-8281010))

[JDK-8278370: [win] Disable Side-by-Side Installations of Multiple JDK Updates in Windows JDK Installers](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8278370)
([JDK-8278370](https://bugs.openjdk.org/browse/JDK-8278370))

_security-libs/java.security_

[Only Expose Certificates With Proper Trust Settings as Trusted Certificate Entries in macOS KeychainStore](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8278449)
(JDK-8278449 (not public))

[RC2 and ARCFOUR Algorithms Added to jdk.security.legacyAlgorithms Security Property](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8286090)
([JDK-8286090](https://bugs.openjdk.org/browse/JDK-8286090))

[Use Larger Default Key Sizes if not Explicitly Specified](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8267319)
([JDK-8267319](https://bugs.openjdk.org/browse/JDK-8267319))

[DES, DESede, and MD5 Algorithms Added to jdk.security.legacyAlgorithms Security Property](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8255552)
([JDK-8255552](https://bugs.openjdk.org/browse/JDK-8255552))

_security-libs/javax.net.ssl_

[Fully Support Endpoint Identification Algorithm in RFC 6125](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-7192189)
([JDK-7192189](https://bugs.openjdk.org/browse/JDK-7192189))

[TLS Cipher Suites using 3DES Removed from the Default Enabled List](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8163327)
([JDK-8163327](https://bugs.openjdk.org/browse/JDK-8163327))

[Change in SSLEngine.closeInbound() Behavior](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8273553)
([JDK-8273553](https://bugs.openjdk.org/browse/JDK-8285497))

_tools/javac_

[Indy String Concat Changes Order of Operations](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8273914)
([JDK-8273914](https://bugs.openjdk.org/browse/JDK-8273914))

[Lambda Deserialization Fails for Object Method References on Interfaces](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8282080)
([JDK-8282080](https://bugs.openjdk.org/browse/JDK-8282080))

_tools/javadoc(tool)_

[JavaDoc Search Enhancements](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8248863)
([JDK-8248863](https://bugs.openjdk.org/browse/JDK-8248863))

_tools/jpackage_

[Allow Per-User and System Wide Configuration of a jpackaged App](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8250950)
([JDK-8250950](https://bugs.openjdk.org/browse/JDK-8250950))

_tools/jshell_

[JShell Highlights Deprecated Elements, Variables, and Keywords](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8274148)
([JDK-8274148](https://bugs.openjdk.org/browse/JDK-8274148))

_tools/launcher_

[`-Xss` May Be Rounded up to a Multiple of the System Page Size](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8236569)
([JDK-8236569](https://bugs.openjdk.org/browse/JDK-8236569))

[Use Larger Default key Sizes if not Explicitly Specified](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8267319)
([JDK-8267319](https://bugs.openjdk.org/browse/JDK-8267319))

_infrastructure_

[Toolchain Upgrade to Visual Studio 2022](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8283723)
([JDK-8283723](https://bugs.openjdk.org/browse/JDK-8283723))

_core-libs/java.lang_

[System Property for Java SE Specification Maintenance Version](https://www.oracle.com/java/technologies/javase/19all-relnotes.html#JDK-8285497)
([JDK-8285497](https://bugs.openjdk.org/browse/JDK-8285497))

### Differences Between Oracle JDK and OpenJDK

- Oracle JDK offers "installers" (msi, rpm, deb, etc.) which not only place the JDK binaries in your system but also
contain update rules and in some cases handle some common configurations like set common environmental variables
(such as, JAVA_HOME in Windows) and establish file associations (such as, use java to launch .jar files). OpenJDK is
offered only as compressed archive (tar.gz or .zip).
- Usage Logging is only available in Oracle JDK.
- Oracle JDK requires that third-party cryptographic providers be signed with a Java Cryptography Extension (JCE)
Code Signing Certificate. OpenJDK continues allowing the use of unsigned third-party crypto providers.
- The output of java -version is different. Oracle JDK returns java and includes the Oracle-specific identifier.
OpenJDK returns OpenJDK and does not include the Oracle-specific identifier.
- Oracle JDK 17 and later are released under the
[Oracle No-Fee Terms and Conditions License](https://www.oracle.com/java/technologies/javase/href=%22https://www.oracle.com/downloads/licenses/no-fee-license.html%22).
OpenJDK is released under [GPLv2wCP](https://openjdk.java.net/legal/gplv2+ce.html). License files included with each
will therefore be different.
- Oracle JDK distributes FreeType under the FreeType license and OpenJDK does so under GPLv2. The contents of
`\legal\java.desktop\freetype.md` is therefore different.
- Oracle JDK has Java cup and steam icons and OpenJDK has Duke icons.
- Oracle JDK source code includes "ORACLE PROPRIETARY/CONFIDENTIAL. Use is subject to license terms." Source code
distributed with OpenJDK refers to the GPL license terms instead.
