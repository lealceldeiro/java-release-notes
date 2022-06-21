# [Java 14](https://docs.oracle.com/en/java/javase/14/) [Release Notes Documentation](https://www.oracle.com/java/technologies/javase/14-relnotes.html)

## [Release Notes](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html)

### New Features and Enhancements

*core-libs*

#### [Accounting Currency Format Support](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8215181)

*core-libs/java.lang*

#### [JEP 359 Records (Preview)](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8222777)

*core-libs/java.nio*

#### [Clarify the Specification of ReadableByteChannel.read() and Related Methods](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8164993)

*hotspot/gc*

#### [JEP 365 ZGC on Windows](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8232364)

#### [JEP 364 ZGC on macOS](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8229358)

#### [Parallel GC Improvements](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8224666)

#### [JEP 345 NUMA-Aware Memory Allocation for G1](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8210473)

*hotspot/jfr*

#### [JEP 349 JFR Event Streaming](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8184193)

JDK Flight Recorder (JFR) now supports continuous monitoring of a Java application by allowing events to be consumed dynamically using a new API located in the jdk.jfr.consumer package

*security-libs/java.security*

#### [Weak Named Curves in TLS, CertPath, and Signed JAR Disabled by Default](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233228)

*security-libs/javax.xml.crypto*

#### [Apache Santuario Library Updated to Version 2.1.4](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231507)

*tools/javac*

#### [Allow Discoverable javac Plugins to be Invoked by Default](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8234211)

*xml/jaxp*

#### [New Method to SAX ContentHandler for Handling XML Declaration](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8230814)

### Removed Features and Options

*core-libs/java.nio.charsets*

#### [Removal of `sun.nio.cs.map` System Property](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8229960)

*deploy*

#### [Removal of `netscape.javascript.JSObjectgetWindow` Method](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8222563)

*hotspot/gc*

#### [JEP 363 Remove the Concurrent Mark and Sweep (CMS) Garbage Collector](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8229049)

*security-libs/java.security*

#### [Removed Deprecated `java.security.acl` APIs](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8191138)

#### [Removal of the Default `keytool -keyalg` Value](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8214024)

*tools/jar*

#### [JEP 367 Remove the Pack200 Tools and API](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8232022)

### Deprecated Features and Options

*core-libs/java.lang*

#### [Thread Suspend/Resume Are Deprecated for Removal](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231602)

The following methods related to thread suspension in `java.lang.Thread` and `java.lang.ThreadGroup` have been terminally deprecated in this release:

- `Thread.suspend()`
- `Thread.resume()`
- `ThreadGroup.suspend()`
- `ThreadGroup.resume()`
- `ThreadGroup.allowThreadSuspension(boolean)`

These methods will be removed in a future release.

*client-libs/javax.swing*

#### [Deprecated NSWindowStyleMaskTexturedBackground](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8240995)

*hotspot/gc*

#### [JEP 366 Deprecate the ParallelScavenge + SerialOld GC Combination](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233301)

*security-libs/javax.crypto*

#### [Deprecated the Legacy Elliptic Curves for Removal](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8234924)

#### [Deprecated the OracleUcrypto JCE Provider for Removal](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8234870)

### Other notes

*client-libs*

#### [Text Visibility Issues in macOS Dark Mode](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8228555)

*core-libs*

#### [Zip File System Throws `java.nio.file.NoSuchFileException` When the File Does Not Exist and Is Not Being Created](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8223771)

*core-libs/java.io:serialization*

#### [Better Serial Filter Handling](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231422)

*core-libs/java.lang*

#### [Thread Interrupt State Is Always Available](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8229516)

#### [`Thread.countStackFrames` Changed to Unconditionally Throw `UnsupportedOperationException`](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8205132)

*core-libs/java.lang.invoke*

#### [`MethodTypefromMethodDescriptorString` Requires "getClassLoader" Permission](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8229785)

#### [`MethodHandlesprivateLookupIn` Requires PRIVATE Lookup Mode](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8173978)

#### [`Lookupin` Throws `IllegalArgumentException` If requestedLookupClass Is a Primitive Type or an Array Class](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8173975)

#### [`MethodHandlesprivateLookupIn` Might Not Produce a Lookup With Full Privilege Access](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233527)

*core-libs/java.net*

#### [`DatagramSocket.send` and `MulticastSocket.send` Throw `IllegalArgumentException` When Socket Is Not Connected and Packet Doesn't Contain Address](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233141)

#### [MulticastSocket `getOption(IP_MULTICAST_IF)` Returns `null` when outgoing interface not set](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233307)

#### [Behavior of MulticastSocket getOption/setOption for IP_MULTICAST_LOOP Conforms With the StandardSocketOptions.IP_MULTICAST_LOOP Specification](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233296)

#### [`InetSocketAddress.toString` Format Changes for IPv6 Literals and Unresolved Addresses](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8225499)

*core-libs/java.nio*

#### [`DatagramChannel.disconnect` Might Leave the Channel's Socket in an Unspecified State](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231260)

*core-libs/java.rmi*

#### [Improve Registry Support](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8230967)

*core-libs/java.text*

#### [Plural Support in CompactNumberFormat](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8222756)

*core-libs/java.util.jar*

#### [ZipFileInputStreamskip handling of negative values](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231451)

*core-libs/java.util:i18n*

#### [Upgraded CLDR to v36](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231273)

*core-libs/javax.lang.model*

#### [`ExecutableElement.getReceiverType` Changed to Return `NOTYPE` Rather Than `null`](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8222369)

*core-libs/javax.naming*

#### [DnsClient TCP Socket Timeout](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8228580)

*core-svc/java.lang.management*

#### [OperatingSystemMXBean Methods Inside a Container Return Container Specific Data](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8226575)

When executing in a container, or other virtualized operating environment, the following OperatingSystemMXBean methods
in this release return container specific information, if available. Otherwise, they return host specific data:

- `getFreePhysicalMemorySize()`
- `getTotalPhysicalMemorySize()`
- `getFreeSwapSpaceSize()`
- `getTotalSwapSpaceSize()`
- `getSystemCpuLoad()`

*hotspot/compiler*

#### [Turned Off AOT by Default and Changed Related Flags to Experimental](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8227439)

*hotspot/gc*

#### [Shenandoah self-fixing barriers](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231087)

#### [Epsilon warns about Xms/Xmx/AlwaysPreTouch configuration](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8232051)

#### [Shenandoah asynchronous object/region pinning](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8232575)

#### [Epsilon does not extend TLABs to max size](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8230646)

#### [Shenandoah supports concurrent class unloading](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8226241)

#### [Shenandoah arraycopy improvements](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231086)

#### [Shenandoah supports JFR Leak Profiler](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8235685)

*hotspot/runtime*

#### [Added `-XX+AdjustStackSizeForTLS` Flag](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8225035)

#### [Detailed Message in `NullPointerExceptions`](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8218628)

#### [CDS Behavior Change With Non-existent Files During Archive Creation](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8227370)

*security-libs/java.security*

#### [Exact Match Required for Trusted TLS Server Certificate](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8227758)

#### [New Checks on Trust Anchor Certificates](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8230318)

#### [Added LuxTrust Global Root 2 Certificate](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8232019)

#### [Added 4 Amazon Root CA Certificates](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233223)

*security-libs/javax.crypto*

#### [Protected `javax.crypto.Cipher` Constructor Throws IAE for Non-null Invalid Arguments](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8233016)

#### [SunJCE Provider Throws NoSuchAlgorithmException for AES/GCM/PKCS5Padding](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8180392)

*security-libs/javax.net.ssl*

#### [Remove Obsolete NIST EC Curves from the Default TLS Algorithms](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8228825)

#### [Removed SSLv2Hello and SSLv3 From Default Enabled TLS Protocols](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8190492)

#### [Stateless Resumption Enabled by Default for JSSE Server](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8228396)

*security-libs/javax.security*

#### [DelegationPermission Allows Creating an Instance That Thows NPE on equals Call](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8231196)

*tools/javac*

#### [`toString()` on Annotation Objects is Consistent Between Core Reflection and `javac`](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8164819)

*xml/javax.xml.transform*

#### [Default ErrorListener No Longer Reports Warnings and Errors to the Console](https://www.oracle.com/java/technologies/javase/14-relnote-issues.html#JDK-8228854)
