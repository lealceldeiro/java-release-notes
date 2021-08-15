# [Java 11](https://docs.oracle.com/en/java/javase/11/index.html) [Release Notes](https://www.oracle.com/technetwork/java/javase/11-relnotes-5012447.html)

## Important Changes

* The deployment stack, required for Applets and Web Start Applications, was deprecated in JDK 9 and has been removed in JDK 11.
* Without a deployment stack, the entire section of supported browsers has been removed from the list of supported configurations of JDK 11.
* Auto-update, which was available for JRE installations on Windows and macOS, is no longer available.
* In Windows and macOS, installing the JDK in previous releases optionally installed a JRE. In JDK 11, this is no longer an option.
* In this release, the JRE or Server JRE is no longer offered. Only the JDK is offered. Users can use `jlink` to create smaller custom runtimes.
* JavaFX is no longer included in the JDK. It is now available as a separate download from [openjfx.io](https://openjfx.io/).
* Java Mission Control, which was shipped in JDK 7, 8, 9, and 10, is no longer included with the Oracle JDK. It is now a separate download.
* Previous releases were translated into English, Japanese, and Simplified Chinese as well as French, German, Italian, Korean, Portuguese (Brazilian), Spanish, and Swedish. However, in JDK 11 and later, French, German, Italian, Korean, Portuguese (Brazilian), Spanish, and Swedish translations are no longer provided.
* Updated packaging format for Windows has changed from tar.gz to .zip, which is more common in Windows OSs.
* Updated package format for macOS has changed from .app to .dmg, which is more in line with the standard for macOS.

## What's New in JDK 11 - New Features and Enhancements

_core-libs/java.lang_

**JEP 327 Unicode 10**

Upgrade existing platform APIs to support version 10.0 of the Unicode Standard (JEP 327: Unicode 10). The JDK 11 release includes support for Unicode 10.0.0. Since the release of JDK 10, which supported Unicode 8.0.0, JDK 11 combines Unicode 9.0.0 and 10.0.0 versions.

_core-libs/java.net_

**JEP 321 HTTP Client (Standard)**

Standardize the incubated HTTP Client API introduced in JDK 9, via JEP 110, and updated in JDK 10 (JEP 321). The HTTP Client has been standarized in Java 11. As part of this work the previously incubating API, located in the `jdk.incubator.http` package, has been removed. At a very minimum, code that uses types from the `jdk.incubator.http` package will need to be updated to import the HTTP types from the standard package name, `java.net.http`.

_core-libs/java.util:collections_

**New Collection.toArray(IntFunction) Default Method**

A new default method toArray(IntFunction) has been added to the `java.util.Collection` interface. This method allows the collection's elements to be transferred to a newly created array of a desired runtime type. The new method is an overload of the existing `toArray(T[])` method that takes an array instance as an argument. The addition of the overloaded method creates a minor source incompatibility. Previously, code of the form `coll.toArray(null)` would always resolve to the existing `toArray` method. With the new overloaded method, this code is now ambiguous and will result in a compile-time error. (This is only a source incompatibility. Existing binaries are unaffected.) The ambiguous code should be changed to cast null to the desired array type, for example, `toArray((Object[]) null)` or some other array type. Note that passing null to either toArray method is specified to throw `NullPointerException`.

_core-libs/java.util:i18n_

**Updated Locale Data to Unicode [CLDR v33](http://cldr.unicode.org/index/downloads/cldr-33)**

The locale data based on the Unicode Consortium's CLDR (Common Locale Data Registry) has been updated for JDK 11. Localized digits that are in supplementary planes (such as, those in Indian Chakma script) are substituted with ASCII digits until JDK-8204092 is resolved. Medium and short time patterns for Burmese locale have not been upgraded. When JDK-8209175 is resolved, these patterns will be upgraded.

_hotspot/compiler_

**Lazy Allocation of Compiler Threads**

A new command line flag `-XX:+UseDynamicNumberOfCompilerThreads` has been added to dynamically control compiler threads. In tiered compilation mode, which is on by default, the VM starts a large number of compiler threads on systems with many CPUs regardless of the available memory and the number of compilation requests. Because the threads consume memory even when they are idle (which is almost all of the time), this leads to an inefficient use of resources.

To address this issue, the implementation has been changed to start only one compiler thread of each type during startup and to handle the start and shutdown of further threads dynamically.

_hotspot/gc_

**JEP 333 ZGC A Scalable Low-Latency Garbage Collector (Experimental)**

The Z Garbage Collector, also known as ZGC, is a scalable low latency garbage collector (JEP 333). It is designed to meet the following goals:

* Pause times do not exceed 10 ms
* Pause times do not increase with the heap or live-set size
* Handle heaps ranging from a few hundred megabytes to multi terabytes in size

At its core, ZGC is a concurrent garbage collector, meaning that all heavy lifting work (marking, compaction, reference processing, string table cleaning, etc) is done while Java threads continue to execute. This greatly limits the negative impact that garbage collection has on application response times.

ZGC is included as an experimental feature. To enable it, the `-XX:+UnlockExperimentalVMOptions` option will therefore need to be used in combination with the `-XX:+UseZGC` option.

This experimental version of ZGC has the following limitations:

* It is only available on Linux/x64.
* Using compressed oops and/or compressed class points is not supported. The `-XX:+UseCompressedOops` and `-XX:+UseCompressedClassPointers` options are disabled by default. Enabling them will have no effect.
* Class unloading is not supported. The `-XX:+ClassUnloading` and `-XX:+ClassUnloadingWithConcurrentMark` options are disabled by default. Enabling them will have no effect.
* Using ZGC in combination with Graal is not supported.

**JEP 318 Epsilon, A No-Op Garbage Collector**

Epsilon GC is the new experimental no-op garbage collector. Epsilon GC only handles memory allocation, and does not implement any memory reclamation mechanism. It is useful for performance testing, to contrast costs/benefits of other GCs. It can be used to conveniently assert memory footprint and memory pressure in tests. In extreme cases, it might be useful with very short lived jobs, where memory reclamation would happen at JVM termination, or getting the last-drop latency improvements in low-garbage applications.

_hotspot/jvmti_

**JEP 331 Low-Overhead Heap Profiling**

Provide a low-overhead way of sampling Java heap allocations, accessible via JVMTI ([JEP 331](http://openjdk.java.net/jeps/331)).

_hotspot/runtime_

**JEP 181 Nest-Based Access Control**

Introduce nests, an access-control context that aligns with the existing notion of nested types in the Java programming language ([JEP-181: Nest-based access control](http://openjdk.java.net/jeps/181)).

_security-libs_

**JEP 324 Key Agreement with Curve25519 and Curve448**

[JEP 324](http://openjdk.java.net/jeps/324) adds an implementation of a new key agreement scheme using Curve25519 and Curve448 as described in RFC 7748. This implementation is available as a Java Cryptography Architecture service, but it has not been incorporated into the new TLS 1.3 implementation.

_security-libs/java.security_

**Added Support for PKCS#1 v2.2 Algorithms Including RSASSA-PSS Signature**

The SunRsaSign and SunJCE providers have been enhanced with support for more algorithms defined in PKCS#1 v2.2, such as RSASSA-PSS signature and OAEP using FIPS 180-4 digest algorithms. New constructors and methods have been added to relevant JCA/JCE classes under the java.security.spec and javax.crypto.spec packages for supporting additional RSASSA-PSS parameters.

_security-libs/javax.crypto_

**Added Brainpool EC Support (RFC 5639)**

The SunEC provider has been enhanced to support 4 additional Brainpool curves as defined in RFC 5639, Elliptic Curve Cryptography (ECC) Brainpool Standard Curves and Curve Generation. The corresponding EC domain parameters can be created by using `java.security.spec.ECGenParameterSpec` objects with standard names of brainpoolP256r1, brainpoolP320r1, brainpoolP384r1, and brainpoolP512r1. Note that the SunJSSE provider has not yet been enhanced to support these brainpool curves.

**JEP 329 ChaCha20 and Poly1305 Cryptographic Algorithms**

Implement the ChaCha20 and ChaCha20-Poly1305 ciphers as specified in RFC 7539. ChaCha20 is a newer stream cipher that can replace the older, insecure RC4 stream cipher.

Those wishing to obtain an instance of the ChaCha20 stream cipher may use the algorithm string "ChaCha20" with the `Cipher.getInstance` method. Those wishing to use ChaCha20 in AEAD mode with the Poly1305 authenticator may use the algorithm string "ChaCha20-Poly1305". At the "Java Security Standard Algorithm Names" document more details can be seen.

**Enhanced KeyStore Mechanisms**

A new security property named `jceks.key.serialFilter` has been introduced. If this filter is configured, the JCEKS KeyStore uses it during the deserialization of the encrypted Key object stored inside a SecretKeyEntry. If it is not configured or if the filter result is UNDECIDED (for example, none of the patterns match), then the filter configured by `jdk.serialFilter` is consulted.

If the system property `jceks.key.serialFilter` is also supplied, it supersedes the security property value defined here.

The filter pattern uses the same format as `jdk.serialFilter`. The default pattern allows `java.lang.Enum`, `java.security.KeyRep`, `java.security.KeyRep$Type`, and `javax.crypto.spec.SecretKeySpec` but rejects all the others.

Customers storing a SecretKey that does not serialize to the above types must modify the filter to make the key extractable.

**RSASSA-PSS Signature Support Added to SunMSCAPI**

The RSASSA-PSS signature algorithm support has been added to the SunMSCAPI provider.

_security-libs/javax.net.ssl_

**JEP 332 Transport Layer Security (TLS) 1.3**

The JDK 11 release includes an implementation of the Transport Layer Security (TLS) 1.3 specification (RFC 8446).

_security-libs/org.ietf.jgss:krb5_

**Support for AES Encryption with HMAC-SHA2 for Kerberos 5 Defined in RFC 8009**

The Kerberos 5 encryption types of `aes128-cts-hmac-sha256-128` and `aes256-cts-hmac-sha384-192` defined in RFC 8009 are supported. These encryption types are enabled by default. The default order of preference is "`aes256-cts-hmac-sha1-96 aes128-cts-hmac-sha1-96 aes256-cts-hmac-sha384-192 aes128-cts-hmac-sha256-128 des3-cbc-sha1 arcfour-hmac-md5 des-cbc-crc des-cbc-md5`".

Users can use the `default_tkt_enctypes` and `default_tgs_enctypes` settings in the `krb5.conf` file to modify the list.

tools/javac

**JEP 323: Local-Variable Syntax for Lambda Parameters**

The reserved type name `var` can now be used when declaring the formal parameters of a lambda expression ([JEP 323](http://openjdk.java.net/jeps/323)). This builds on the ability in Java SE 10 to use `var` when declaring local variables.

Using `var` for a formal parameter of a lambda expression causes the type of the parameter to be inferred, using the same rules as when neither `var` nor an explicit type is present. Lambda expressions have allowed their formal parameters to be declared without explicit types since Java SE 8.

If `var` is used for any formal parameter of a lambda expression, then it must be used for all formal parameters of that lambda expression.

_tools/launcher_

**JEP 330 Launch Single-File Source-Code Programs**

Enhance the java launcher to run a program supplied as a single file of Java source code, including usage from within a script by means of "shebang" files and related techniques.

## Removed Features and Options

_client-libs_

**Removal of com.sun.awt.AWTUtilities Class**

The com.sun.awt.AWTUtilities class was deprecated with forRemoval=true in JDK 10 (JDK-8187253). This class was unused in the JDK and has been removed in this release.

_client-libs/2d_

**Removal of Lucida Fonts from Oracle JDK**

Oracle JDK no longer ships any fonts and relies entirely on fonts installed on the operating system.

This means that fonts in the Bigelow & Holmes Lucida family (Lucida Sans, Lucida Bright, and Lucida Typewriter) are no longer available to applications from the JDK.

If applications rely on fonts shipped in the JDK, they may need to be updated.

If system adminstrators are running Java server applications that rely on fonts shipped in the JDK rather than on system font packages, then the applications may fail to run until the system font packages are installed.

_client-libs/java.awt_

**Removal of `appletviewer` Launcher**

The `appletviewer` tool was deprecated in JDK 9 (see [JDK-8074165](http://bugs.java.com/view_bug.do?bug_id=JDK-8074165)) and removed in this release.

_client-libs/javax.imageio_

**Oracle JDK's javax.imageio JPEG Plugin No Longer Supports Images with alpha**

_core-libs_

**Removal of sun.misc.Unsafe.defineClass**

The `sun.misc.Unsafe.defineClass` class has been removed. Users should use the public replacement, `java.lang.invoke.MethodHandles.Lookup.defineClass`, added in Java SE 9. More info at https://docs.oracle.com/javase/9/docs/api/java/lang/invoke/MethodHandles.Lookup.html#defineClass-byte:A-

_core-libs/java.lang_

**Removal of Thread.destroy() and Thread.stop(Throwable) Methods**

The methods `Thread.destroy()` and `Thread.stop(Throwable)` have been removed. They have been deprecated for several Java SE releases. The `Thread.destroy()` method has never been implemented, and the `Thread.stop(Throwable)` method has been non-functional since Java SE 8. No code should rely on the behavior of these two methods; however, any code that uses these methods will cause compilation errors. The mitigation is to remove references to these methods from the source code. Note that the no-arg method `Thread.stop()` is unaffected by this change.

_core-libs/java.nio_

**Removal of sun.nio.ch.disableSystemWideOverlappingFileLockCheck Property**

The property `sun.nio.ch.disableSystemWideOverlappingFileLockCheck` has been removed. Consequently, compatibility with the older locking approach has also been removed.

_core-libs/java.util:i18n_

**Removal of sun.locale.formatasdefault Property**

The system property `sun.locale.formatasdefault`, introduced in JDK 7 for backwards compatibility, has been removed.

_core-svc/javax.management_

**Removal of JVM-MANAGEMENT-MIB.mib**

The specification for JVM monitoring and management through SNMP `JVM-MANAGEMENT-MIB.mib` has been removed. Customers can use JMX to monitor and manage a running JVM and to access the standard set of metrics and operations.

_core-svc/tools_

**Removal of SNMP Agent**

The jdk.snmp module has been removed.

_deploy_

**Removal of Java Deployment Technologies**

The Java Plugin and Java WebStart technologies that were deprecated in JDK 9 and marked as candidates for removal in JDK 10, have now been removed. The Java Control Panel, which was used for configuring the deployment technologies, has also been removed along with the shared system JRE (but not the server JRE) and the JRE Auto Update mechanism. More details are available in this white paper.

_infrastructure_

**Removal of JMC from the Oracle JDK**

Java Mission Control (JMC) is no longer included in the JDK bundles. A stand-alone version of JMC, compatible with Oracle JDK 11 and OpenJDK 11, is available as a separate download.

_javafx/other_

**Removal of JavaFX from the Oracle JDK**

The JavaFX modules have been removed from the JDK 11 release. These modules were included in earlier releases of the Oracle JDK, but not in the OpenJDK releases. The JavaFX modules will be available as a separate set of modules outside the JDK. More details are available in this [white paper(http://www.oracle.com/technetwork/java/javase/javaclientroadmapupdate2018mar-4414431.pdf)

_other-libs_

**JEP 320 Remove the Java EE and CORBA Modules**

Remove the Java EE and CORBA modules from the Java SE Platform and the JDK. These modules were deprecated in Java SE 9 with the declared intent to remove them in a future release ([JEP 320](http://openjdk.java.net/jeps/320)).

## Deprecated Features and Options

_core-libs/java.util.concurrent_

**`ThreadPoolExecutor` Should Not Specify a Dependency on Finalization**

Previous versions of `ThreadPoolExecutor` had a finalize method that shut down the thread pool, but in this version the `finalize` method does nothing. This should have no visible effect unless a subclass explicitly invokes the finalize method and relies on the executor being shutdown.

_docs_

**JEP 335 Deprecate the Nashorn JavaScript Engine**

Deprecate the Nashorn JavaScript script engine and APIs, and the jjs tool, with the intent to remove them in a future release ([JEP 335](http://openjdk.java.net/jeps/335)).

The Nashorn JavaScript Engine implementation, the APIs and the `jjs` shell tool have been deprecated and might be removed in a future release. Code that uses classes and interfaces from `jdk.nashorn.api.scripting` and `jdk.nashorn.api.tree` packages will get a deprecation warning from `javac`.

_hotspot/compiler_

**Deprecate -XX+AggressiveOpts**

The VM option `-XX:+AggressiveOpts` is deprecated in JDK 11 and will be removed in a future release. The option was originally supposed to enable experimental optimizations of the C2 compiler to improve performance of specific benchmarks. Most features have been removed or integrated over time leaving the behavior of the option ill-defined and error-prone. The only effect that the flag currently has is setting `AutoBoxCacheMax` to 20000 and `BiasedLockingStartupDelay` to 500. The same configuration can be achieved by setting their corresponding flags from the command line. Therefore, `-XX:+AggressiveOpts` will no longer be available in a future release.

_hotspot/runtime_

**Obsolete Support for Commercial Features**

The `-XX:+UnlockCommercialFeatures` and `-XX:+LogCommercialFeatures` command line arguments have been obsoleted, and will generate a warning message if used. The command line arguments used to control the use of and logging for commercial/licensed features in the VM. Since there are no such features anymore the command line arguments are no longer useful.

Similarly, the `VM.unlock_commercial_features` and `VM.check_commercial_features` `jcmd` commands will also generate a warning message but have no additional effect.

_security-libs/org.ietf.jgss_

**Deprecate Stream-Based GSSContext Methods**

The stream-based methods in `GSSContext` have been deprecated in this release since GSS-API works on opaque tokens and has not defined a wire protocol. This includes the overloaded forms of the `initSecContext`, `acceptSecContext`, `wrap`, `unwrap`, `getMIC`, and `verifyMIC` methods that have an `InputStream` argument. These methods have already been removed in RFC 8353.

_tools_

**JEP 336 Deprecate the Pack200 Tools and API**

Deprecate the `pack200` and `unpack200` tools, and the Pack200 API in `java.util.jar` ([JEP 336](http://openjdk.java.net/jeps/336)).

The pack200 API and the tools associated with it, pack200 and unpack200, have been deprecated and will be removed in a future release.

Those tools are still included in JDK 11, but will no longer be updated to support the latest class file format. Class files with unknown attributes will be passed-through without compression.

## Other

_core-libs/java.lang_

**Make Some System Properties Effectively readonly**

The values of `java.home`, `user.home`, `user.dir`, and `user.name` properties are cached at startup. Changes made using `System::setProperty` after startup will not change the behavior of APIs in the java.base module.

_security-libs/java.security_

**Added GoDaddy Root Certificates**

**Removal of Baltimore Cybertrust Code Signing CA**

**Removal of SECOM Root Certificate**

**Added T-Systems, GlobalSign and Starfield Services Root Certificates**

**Removal of AOL and Swisscom Root Certificates**

**Removal of Several Symantec Root CAs**

**Added Entrust Root Certificates**
