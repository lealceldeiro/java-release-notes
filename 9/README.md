# [Java 9](https://docs.oracle.com/javase/9/) [Release Notes](https://www.oracle.com/technetwork/java/javase/9-relnotes-3622618.html)


## [What's new in JDK 9](https://docs.oracle.com/javase/9/whatsnew/toc.htm#JSNEW-GUID-C23AFD78-C777-460B-8ACE-58BE5EA681F6)

### Key Changes in JDK 9

* Java Platform Module System: Introduces a new kind of Java programing component, the module, which is a named, self-describing collection of code and data. This module system:
 
   - Introduces a new optional phase: link time, see the [`jlink`](https://docs.oracle.com/javase/9/tools/jlink.htm#JSWOR-GUID-CECAC52B-CFEE-46CB-8166-F17A8E9280E9) tool documentation and these **[examples](./jlink)**.
   - Adds options to the tools `javac`, `jlink`, and `java` where you can specify module paths, which locate definitions of modules.
   - Introduces the modular JAR file, which is a JAR file with a `module-info.class` file in its root directory.
   - Introduces the *JMOD* format, which is a packaging format similar to JAR except it can include native code and configuration files; see the [`jmod`](https://docs.oracle.com/javase/9/tools/jmod.htm#JSWOR-GUID-0A0BDFF6-BE34-461B-86EF-AAC9A555E2AE) tool.
   - The JDK itself has been divided into a set of modules. This change:
     - Enables you to combine the JDK's modules into a variety of configurations.
     - Restructures the JDK and JRE runtime images to accommodate modules and improve performance, security, and maintainability.
     - Defines a new URI scheme for naming modules, classes, and resources stored in a runtime image without revealing the internal structure or format of the image: `jrt`. A *jrt* URL is a hierarchical URI, per [RFC 3986](tools.ietf.org/html/rfc3986), with the syntax `jrt:/[$MODULE[/$PATH]]`. More info at [JEP 220: Modular Run-Time Images](https://openjdk.java.net/jeps/220)
     - Removes the endorsed-standards override mechanism and the extension mechanism.
       + Before Java 9, the extension mechanism let us add classes to the JDK without having to place them on the class path. It loaded them from directories named by the system property `java.ext.dirs`, from `lib/ext` in the JRE, or from a platform-specific system-wide directory. Likewise the endorsed standards override mechanism let us replace certain APIs with custom implementations. It loaded them from the directories named by the system property `java.endorsed.dirs` or the `lib/endorsed` directory in the JRE. Aftet Java 9 removed these features, alternatives are as follows:
           - The `java` and `javac` option `--patch-module` injects content into modules.
           - The `java` and `javac` option `--upgrade-module-path` replaces an upgradeable platform module with another one.
           - The extending artifacts can be placed on the class path.
     - Removes `rt.jar` and `tools.jar` from the Java runtime image.
     - Makes most of the JDK's internal APIs inaccessible by default but leaves a few critical, widely used internal APIs accessible until supported replacements exist for all or most of their functionality.
        + To determine if some code uses internal JDK APIs, run the command `jdeps -jdkinternals`.
 
   - More info at [Java Platform Module System (JSR 376)](http://openjdk.java.net/projects/jigsaw/spec/)
     - [JEP 261: Module System](http://openjdk.java.net/jeps/261)
     - [JEP 200: The Modular JDK](http://openjdk.java.net/jeps/200)
     - [JEP 220: Modular Run-Time Images](http://openjdk.java.net/jeps/220) and [JEP 260: Encapsulate Most Internal APIs](http://openjdk.java.net/jeps/260).
 
* [JEP 223: New Version-String Scheme](http://openjdk.java.net/jeps/223): Provides a simplified version-string format that helps to clearly distinguish major, minor, security, and patch update releases. The new version-string format is `$MAJOR.$MINOR.$SECURITY.$PATCH`.

### What’s New for the Java Language in JDK 9

* [JEP 213: Milling Project Coin](http://openjdk.java.net/jeps/213) (_more at [Java Language Changes for Java SE 9](https://docs.oracle.com/javase/9/language/toc.htm#JSLAN-GUID-16A5183A-DC0D-4A96-B9D8-AAC9671222DD)_)
  - Allow `@SafeVargs` on private instance methods.
  - Allow effectively final variables to be used as resources in the `try-with-resources` statement.
  - Allow the diamond with anonymous classes if the argument type of the inferred type is denotable.
  - Complete the removal, begun in Java SE 8, of the underscore from the set of legal identifier names.
  - Add support for private interface methods.

### What’s New for Javadoc in JDK 9

* [JEP 221: Simplified Doclet API](http://openjdk.java.net/jeps/221)
  - Replaces the old Doclet API with a new simplified API that leverages other standard, existing APIs. The standard doclet has been rewritten to use the new [Doclet API](https://docs.oracle.com/javase/9/docs/api/jdk/javadoc/doclet/package-summary.html).
* [JEP 224: HTML5 Javadoc](http://openjdk.java.net/jeps/224)
  - Supports generating HTML5 output. To get fully compliant HTML5 output, any HTML content provided in documentation comments must be compliant with HTML5.
* [JEP 225: Javadoc Search](http://openjdk.java.net/jeps/225)
  - Provides a search box to the generated API documentation. This search box can be used to find program elements, tagged words, and phrases within the documentation.
* [JEP 261: Module System](http://openjdk.java.net/jeps/261)
  - Supports documentation comments in module declarations. Includes new command-line options to configure the set of modules to be documented and generates a new summary page for any modules being documented.

### What’s New for Internationalization in JDK 9

* [JEP 267: Unicode 8.0](http://openjdk.java.net/jeps/267)
* [JEP 252: CLDR Locale Data Enabled by Default](http://openjdk.java.net/jeps/252)
* [JEP 226: UTF-8 Properties Files](http://openjdk.java.net/jeps/226)
 
### What’s New for the JDK 9 Installer

* Installer Enhancements for Microsoft Windows
  - Enable or Disable Web Deployment with Installer's UI.
* Installer Enhancements for macOS
  - Provides notification on next CPU availability after uninstalling the current CPU version.
  - Enhanced user experience while updating the JRE.
  
### What’s New for Tools in JDK 9

* [JEP 222: jshell: The Java Shell (Read-Eval-Print Loop)](http://openjdk.java.net/jeps/222): Adds Read-Eval-Print Loop (REPL) functionality to the Java platform.
* [JEP 228: Add More Diagnostic Commands](http://openjdk.java.net/jeps/228): Defines additional diagnostic commands to improve the ability to diagnose issues with Hotspot and the JDK. More info at [jcmd](https://docs.oracle.com/javase/9/tools/jcmd.htm#JSWOR743) and [Diagnostic Tools](https://docs.oracle.com/javase/9/troubleshoot/diagnostic-tools.htm#JSTGD-GUID-CBC97A20-7379-4762-BA17-FB1A560D02E4).
* [JEP 231: Remove Launch-Time JRE Version Selection](http://openjdk.java.net/jeps/231): Removes the ability to request a version of the JRE that is not the JRE being launched at launch time.
* [JEP 238: Multi-Release JAR Files](http://openjdk.java.net/jeps/238): Extends the JAR file format to enable multiple, Java release-specific versions of class files to coexist in a single archive. A multirelease JAR (MRJAR) contains additional, versioned directories for classes and resources specific to particular Java platform releases. Specify versioned directories with the [`jar`](https://docs.oracle.com/javase/9/tools/jar.htm#JSWOR-GUID-51C11B76-D9F6-4BC2-A805-3C847E857867) tool's `--release` option.
* [JEP 240: Remove the JVM TI hprof Agent](http://openjdk.java.net/jeps/240): Removes the hprof agent from the JDK. The hprof agent was written as demonstration code for the JVM Tool Interface and not intended to be a production tool.
* [JEP 241: Remove the jhat Tool](http://openjdk.java.net/jeps/241): Removes the `jhat` tool from the JDK. The `jhat` tool was an experimental and unsupported tool added in JDK 6. It is out of date; superior heap visualizers and analyzers have been available for many years.
* [JEP 245: Validate JVM Command-Line Flag Arguments](http://openjdk.java.net/jeps/245): Validates arguments to all numerical JVM command-line flags to avoid failures and instead displays an appropriate error message if they are found to be invalid.
* [JEP 247: Compile for Older Platform Versions](http://openjdk.java.net/jeps/247): Enhances `javac` so that it can compile Java programs to run on selected earlier versions of the platform. When using the `-source` or `-target` options, the compiled program might accidentally use APIs that are not supported on the given target platform. The `--release` option will prevent accidental use of APIs. `--release N` is roughly equivalent to:
  
  - for N < 9: `-source N -target N -bootclasspath <documented-APIs-from-N>`,
  - for N >= 9: `-source N -target N --system <documented-APIs-from-N>`.

* [JEP 282: jlink: The Java Linker](http://openjdk.java.net/jeps/282): Assembles and optimizes a set of modules and their dependencies into a custom runtime image as defined in [JEP 220](http://openjdk.java.net/jeps/220).

### What’s New for Security in JDK 9

* [JEP 219: Datagram Transport Layer Security (DTLS)](http://openjdk.java.net/jeps/219): Enables Java Secure Socket Extension (JSSE) API and the SunJSSE security provider to support DTLS Version 1.0 and DTLS Version 1.2 protocols.
* [JEP 244: TLS Application-Layer Protocol Negotiation Extension](http://openjdk.java.net/jeps/244): Enables the client and server in a Transport Layer Security (TLS) connection to negotiate the application protocol to be used. With Application-Layer Protocol Negotiation (ALPN), the client sends the list of supported application protocols as part of the TLS ClientHello message. The server chooses a protocol and returns the selected protocol as part of the TLS ServerHello message. The application protocol negotiation can be accomplished within the TLS handshake, without adding network round-trips.
* [JEP 249: OCSP Stapling for TLS](http://openjdk.java.net/jeps/249)
  - Enables the server in a TLS connection to check for a revoked X.509 certificate revocation. The server does this during TLS handshaking by contacting an Online Certificate Status Protocol (OCSP) responder for the certificate in question. It then attaches or "staples" the revocation information to the certificate that it returns to the client so that the client can take appropriate action.
  - Enables the client to request OCSP stapling from a TLS server. The client checks stapled responses from servers that support the feature.
* [JEP 246: Leverage CPU Instructions for GHASH and RSA](http://openjdk.java.net/jeps/246)
  - Improves performance ranging from 34x to 150x for AES/GCM/NoPadding using GHASH HotSpot intrinsics. GHASH intrinsics are accelerated by the PCLMULQDQ instruction on Intel x64 CPU and the xmul/xmulhi instructions on SPARC.
  - Improves performance up to 50% for `BigInteger` `squareToLen` and `BigInteger` `mulAdd` methods using RSA HotSpot intrinsics.
  - RSA intrinsics apply to the `java.math.BigInteger` class on Intel x64.
  - A new security property `jdk.security.provider.preferred` is introduced to configure providers that offer significant performance gains for specific algorithms.
* [JEP 273: DRBG-Based SecureRandom Implementations](http://openjdk.java.net/jeps/273)
  - Provides the functionality of Deterministic Random Bit Generator (DRBG) mechanisms as specified in [NIST SP 800-90Ar1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-90Ar1.pdf) in the [`SecureRandom`](https://docs.oracle.com/javase/9/docs/api/java/security/SecureRandom.html) API.
  - The DRBG mechanisms use modern algorithms as strong as SHA-512 and AES-256.
  - Each of these mechanisms can be configured with different security strengths and features to match user requirements.
* [JEP 288: Disable SHA-1 Certificates](http://openjdk.java.net/jeps/288)
  - Improves the security configuration of the JDK by providing a more flexible mechanism to disable X.509 certificate chains with SHA-1-based signatures
  - Disables SHA-1 in TLS Server certificate chains anchored by roots included by default in the JDK; local or enterprise certificate authorities (CAs) are not affected.
* [JEP 229: Create PKCS12 Keystores by Default](http://openjdk.java.net/jeps/229)
  - Modifies the default keystore type from JKS to PKCS12. [PKCS#12](http://www.emc.com/emc-plus/rsa-labs/standards-initiatives/pkcs12-personal-information-exchange-syntax-standard.htm) is an extensible, standard, and widely supported format for storing cryptographic keys. PKCS12 keystores improve confidentiality by storing private keys, trusted public key certificates, and secret keys. This feature also opens opportunities for interoperability with other systems such as Mozilla, Microsoft's Internet Explorer, and OpenSSL that support PKCS12.
  - The SunJSSE provider supplies a complete implementation of the PKCS12 `java.security.KeyStore` format for reading and writing PKCS12 files.
* [JEP 287: SHA-3 Hash Algorithms](http://openjdk.java.net/jeps/287)
  - Supports SHA-3 cryptographic hash functions as specified in [NIST FIPS 202](http://nvlpubs.nist.gov/nistpubs/FIPS/NIST.FIPS.202.pdf).
  - The following additional standard algorithms are supported by the `java.security.MessageDigest` API: SHA3-224, SHA3-256, SHA3-384, and SHA3-512.
  - The following providers support SHA-3 algorithm enhancements:
     + SUN provider: SHA3-224, SHA3-256, SHA3-384, and SHA3-512
     + OracleUcrypto provider: SHA-3 digests supported by Solaris 12.0
 
### What’s New for Deployment in JDK 9
 
* [Deprecate the Java Plug-in](https://blogs.oracle.com/java-platform-group/further-updates-to-moving-to-a-plugin-free-web)
  - Deprecates the Java Plug-in and associated applet technologies in Oracle's JDK 9 builds. While still available in JDK 9, these technologies will be considered for removal from the Oracle JDK and JRE in a future release.
  - Applets and JavaFX applications embedded in a web page require the Java Plug-in to run. It should be considered to rewrite these types of applications as Java Web Start or self-contained applications.
* Enhanced Java Control Panel
  - Improves the grouping and presentation of options within the Java Control Panel. Information is easier to locate, a search field is available, and modal dialog boxes are no longer used.
  - The location of some options has changed from previous versions of the Java Control Panel.
* [JEP 275: Modular Java Application Packaging](http://openjdk.java.net/jeps/275)
  - Integrates features from Project Jigsaw into the Java Packager, including module awareness and custom runtime creation.
  - Leverages the [`jlink`](https://docs.oracle.com/javase/9/tools/jlink.htm#JSWOR-GUID-CECAC52B-CFEE-46CB-8166-F17A8E9280E9) tool to create smaller packages.
  - Creates applications that use the JDK 9 runtime only. Cannot be used to package applications with an earlier release of the JRE.
* [JEP 289: Deprecate the Applet API](http://openjdk.java.net/jeps/289): Deprecates the Applet API, which is becoming less useful as web browser vendors remove support for Java browser plug-ins. While still available in JDK 9, the Applet class will be considered for removal in a future release. Consider rewriting applets as Java Web Start or self-contained applications.

### What’s New for the JVM in JDK 9

* [JEP 165: Compiler Control](http://openjdk.java.net/jeps/165): Provides a way to control JVM compilation through compiler directive options. The level of control is runtime-manageable and method-specific. Compiler Control supersedes, and is backward compatible, with CompileCommand.
* [JEP 197: Segmented Code Cache](http://openjdk.java.net/jeps/197): Divides the code cache into distinct segments, each of which contains compiled code of a particular type, to improve performance and enable future extensions.
* [JEP 276: Dynamic Linking of Language-Defined Object Models](http://openjdk.java.net/jeps/276)

### What’s New for JVM Tuning in JDK 9

* Improve G1 Usability, Determinism, and Performance
* [JEP 158: Unified JVM Logging](http://openjdk.java.net/jeps/158) (_more info at the `-Xloggc java` option_)
* [JEP 214: Remove GC Combinations Deprecated in JDK 8](http://openjdk.java.net/jeps/214)
  - This means that the following GC combinations no longer exist:
    + DefNew + CMS
    + ParNew + SerialOld
    + Incremental CMS
  - The "foreground" mode for Concurrent Mark Sweep (CMS) has also been removed. The following command-line flags have been removed:
    + `-Xincgc`
    + `-XX:+CMSIncrementalMode`
    + `-XX:+UseCMSCompactAtFullCollection`
    + `-XX:+CMSFullGCsBeforeCompaction`
    + `-XX:+UseCMSCollectionPassing`
  - The command line flag `-XX:+UseParNewGC` no longer has an effect. `ParNew` can only be used with `CMS` and `CMS` requires `ParNew`. Thus, the `-XX:+UseParNewGC` flag has been deprecated and will likely be removed in a future release.
* [JEP 248: Make G1 the Default Garbage Collector](http://openjdk.java.net/jeps/248)
* [JEP 271: Unified GC Logging](http://openjdk.java.net/jeps/271)
* [JEP 291: Deprecate the Concurrent Mark Sweep (CMS) Garbage Collector](http://openjdk.java.net/jeps/291)

### What’s New for Core Libraries in JDK 9

* [JEP 102: Process API Updates](http://openjdk.java.net/jeps/102)
* [JEP 193: Variable Handles](http://openjdk.java.net/jeps/193)
* [JEP 254: Compact Strings](http://openjdk.java.net/jeps/254)
* [JEP 264: Platform Logging API and Service](http://openjdk.java.net/jeps/264)
* [JEP 266: More Concurrency Updates](http://openjdk.java.net/jeps/266)
* [JEP 268: XML Catalogs](http://openjdk.java.net/jeps/268)
* [JEP 269: Convenience Factory Methods for Collections](http://openjdk.java.net/jeps/269): Makes it easier to create instances of collections and maps with small numbers of elements. New static factory methods on the List, Set, and Map interfaces make it simpler to create immutable instances of those collections. i.e.: `Set<String> alphabet = Set.of("a", "b", "c");`
* [JEP 274: Enhanced Method Handles](http://openjdk.java.net/jeps/274)
* [JEP 277: Enhanced Deprecation](http://openjdk.java.net/jeps/277): Revamps the @Deprecated annotation to provide better information about the status and intended disposition of an API in the specification. Two new elements have been added:
  - `@Deprecated(forRemoval=true)` indicates that the API will be removed in a future release of the Java SE platform.
  - `@Deprecated(since="version")` contains the Java SE version string that indicates when the API element was deprecated, for those deprecated in Java SE 9 and beyond.
* [JEP 285: Spin-Wait Hints](http://openjdk.java.net/jeps/285)
* [JEP 290: Filter Incoming Serialization Data](http://openjdk.java.net/jeps/290)
* [JEP 259: Stack-Walking API](http://openjdk.java.net/jeps/259)
* [JEP 255: Merge Selected Xerces 2.11.0 Updates into JAXP](https://bugs.openjdk.java.net/browse/JDK-8044086)

### What's New for Nashorn in JDK 9

* [JEP 236: Parser API for Nashorn](http://openjdk.java.net/jeps/236)
* [JEP 292: Implement Selected ECMAScript 6 Features in Nashorn](http://openjdk.java.net/jeps/292)

### What’s New for Client Technologies in JDK 9

* [JEP 251: Multi-Resolution Images](http://openjdk.java.net/jeps/251)
* [JEP 253: Prepare JavaFX UI Controls and CSS APIs for Modularization](https://openjdk.java.net/jeps/253)
* [JEP 256: BeanInfo Annotations](http://openjdk.java.net/jeps/256)
* [JEP 262: TIFF Image I/O](http://openjdk.java.net/jeps/262)
* [JEP 263: HiDPI Graphics on Windows and Linux](http://openjdk.java.net/jeps/263)
* [JEP 272: Platform-Specific Desktop Features](http://openjdk.java.net/jeps/272)
* [JEP 283: Enable GTK 3 on Linux](http://openjdk.java.net/jeps/283)

## [Important Changes and Information](https://www.oracle.com/technetwork/java/javase/9-relnote-issues-3704069.html)

## [Enhancements and Notes](https://www.oracle.com/technetwork/java/javase/9-new-features-3745613.html)

## [Removed APIs, Features, and Options](https://www.oracle.com/technetwork/java/javase/9-removed-features-3745614.html)

## [Deprecated APIs, Features, and Options](https://www.oracle.com/technetwork/java/javase/9-deprecated-features-3745636.html)

## [Other Notes](https://www.oracle.com/technetwork/java/javase/9-notes-3745703.html)

## [Java Mission Control 6.0 Release Notes](https://www.oracle.com/technetwork/java/javase/jmc6-release-notes-3689600.html)
