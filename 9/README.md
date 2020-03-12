# [Java 9](https://docs.oracle.com/javase/9/) [Release Notes](https://www.oracle.com/technetwork/java/javase/9-relnotes-3622618.html)


## [What's new in JDK 9](https://docs.oracle.com/javase/9/whatsnew/toc.htm#JSNEW-GUID-C23AFD78-C777-460B-8ACE-58BE5EA681F6)

### Key Changes in JDK 9

 * Java Platform Module System: Introduces a new kind of Java programing component, the module, which is a named, self-describing collection of code and data. More info at
   - [Java Platform Module System (JSR 376)](http://openjdk.java.net/projects/jigsaw/spec/)
   - [JEP 261: Module System](http://openjdk.java.net/jeps/261)
   - [JEP 200: The Modular JDK](http://openjdk.java.net/jeps/200)
   - [JEP 220: Modular Run-Time Images](http://openjdk.java.net/jeps/220) and [JEP 260: Encapsulate Most Internal APIs](http://openjdk.java.net/jeps/260).
 * [JEP 223: New Version-String Scheme](http://openjdk.java.net/jeps/223): Provides a simplified version-string format that helps to clearly distinguish major, minor, security, and patch update releases. The new version-string format is `$MAJOR.$MINOR.$SECURITY.$PATCH`.
 
### What’s New for the JDK 9 Installer

* Installer Enhancements for Microsoft Windows
  - Enable or Disable Web Deployment with Installer's UI.
* Installer Enhancements for macOS
  - Provides notification on next CPU availability after uninstalling the current CPU version.
  - Enhanced user experience while updating the JRE.
  
### What’s New for Tools in JDK 9

* [JEP 222: jshell: The Java Shell (Read-Eval-Print Loop)](http://openjdk.java.net/jeps/222): Adds Read-Eval-Print Loop (REPL) functionality to the Java platform.
* [JEP 228: Add More Diagnostic Commands](http://openjdk.java.net/jeps/228): Defines additional diagnostic commands to improve the ability to diagnose issues with Hotspot and the JDK.
* [JEP 231: Remove Launch-Time JRE Version Selection](http://openjdk.java.net/jeps/231): Removes the ability to request a version of the JRE that is not the JRE being launched at launch time.
* [JEP 238: Multi-Release JAR Files](http://openjdk.java.net/jeps/238): Extends the JAR file format to enable multiple, Java release-specific versions of class files to coexist in a single archive. A multirelease JAR (MRJAR) contains additional, versioned directories for classes and resources specific to particular Java platform releases. Specify versioned directories with the [`jar`](https://docs.oracle.com/javase/9/tools/jar.htm#JSWOR-GUID-51C11B76-D9F6-4BC2-A805-3C847E857867) tool's `--release` option.
* [JEP 240: Remove the JVM TI hprof Agent](http://openjdk.java.net/jeps/240): Removes the hprof agent from the JDK. The hprof agent was written as demonstration code for the JVM Tool Interface and not intended to be a production tool.
* [JEP 241: Remove the jhat Tool](http://openjdk.java.net/jeps/241): Removes the `jhat` tool from the JDK. The `jhat` tool was an experimental and unsupported tool added in JDK 6. It is out of date; superior heap visualizers and analyzers have been available for many years.
* [JEP 245: Validate JVM Command-Line Flag Arguments](http://openjdk.java.net/jeps/245): Validates arguments to all numerical JVM command-line flags to avoid failures and instead displays an appropriate error message if they are found to be invalid.
* [JEP 247: Compile for Older Platform Versions](http://openjdk.java.net/jeps/247): Enhances `javac` so that it can compile Java programs to run on selected earlier versions of the platform. When using the `-source` or `-target` options, the compiled program might accidentally use APIs that are not supported on the given target platform. The `--release` option will prevent accidental use of APIs.
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
 
