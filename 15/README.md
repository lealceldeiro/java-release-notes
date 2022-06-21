# [Java 15](https://docs.oracle.com/en/java/javase/15/) [Release Notes Documentation](https://www.oracle.com/java/technologies/javase/15-relnotes.html)

## [Release Notes](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html)

### New Features and Enhancements

*core-libs/java.lang*
#### [Added `isEmpty` Default Method to CharSequence](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8215401)

*core-libs/java.lang*

#### [Support for Unicode 13.0](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8239383)

*core-libs/java.lang.invoke*

#### [JEP 371 Hidden Classes](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8238358)

*core-libs/java.net*

#### [Added Support for SO_INCOMING_NAPI_ID Support](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8243099)

*core-libs/java.util:collections*

#### [Specialized Implementations of TreeMap Methods](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8176894)

*core-svc/javax.management*

#### [Added Ability to Configure Third Port for Remote JMX](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8234484)

*core-svc/tools*

#### [New Option Added to `jstatd` for Specifying RMI Connector Port Number](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8196729)

#### [New Option Added to jcmd for Writing a gzipped Heap Dump](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8237354)

*tools/javac*

#### [JEP 378 Text Blocks](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8236934)

*hotspot/svc-agent*

#### [New Options Added to `jhsdb` for `debugd` Mode](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8196751)

*install/install*

#### [Oracle JDK Installer for Windows Provides Executables (javac, etc) in a Path Reachable From Any Command Prompt](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8222383)

*security-libs/java.security*

#### [Added Revocation Checking to jarsigner](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8242060)

#### [Tools Warn If Weak Algorithms Are Used](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8172404)

*security-libs/javax.crypto*

#### [SunJCE Provider Supports SHA-3 Based Hmac Algorithms](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8172680)

*security-libs/javax.net.ssl*

#### [New System Properties to Configure the TLS Signature Schemes](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8242141)

#### [Support for certificate_authorities Extension](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8206925)

*security-libs/org.ietf.jgss:krb5*

#### [Support for canonicalize in krb5.conf](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8239385)

#### [Support cross-realm MSSFU](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8005819)

### Removed Features and Options

*core-libs/java.net*

#### [Removal of Terminally Deprecated Solaris-specific SO_FLOW_SLA Socket Option](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8244582)

*core-libs/java.rmi*

#### [Removal of RMI Static Stub Compiler (rmic)](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8225319)

*core-svc/javax.management*

#### [Removal of Deprecated Constant RMIConnectorServer.CREDENTIAL_TYPES](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8213222)

*core-libs/jdk.nashorn*

#### [Removal of Nashorn JavaScript Engine](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8236933)

*hotspot/gc*

#### [Obsolete -XXUseAdaptiveGCBoundary](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8228991)

*security-libs/java.security*

#### [Removal of Comodo Root CA Certificate](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8225069)

#### [Removal of DocuSign Root CA Certificate](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8225068)

*security-libs/javax.net.ssl*

#### [Retired the Deprecated SSLSession.getPeerCertificateChain() Method Implementation](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8241039)

#### [Removal of com.sun.net.ssl.internal.ssl.Provider Name](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8219989)

### Deprecated Features and Options

*core-libs/java.rmi*

#### [Deprecated RMI Activation for Removal](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8245068)

*docs*

#### [Deprecated NSWindowStyleMaskTexturedBackground](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8240995)

*hotspot/gc*

#### [Deprecated -XXForceNUMA Option](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8243628)

*hotspot/runtime*

#### [Disabled Biased-locking and Deprecated Biased-locking Flags](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8231264)

*security-libs/javax.crypto*

#### [Disabled Native SunEC Implementation by Default](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8237219)

*security-libs/jdk.security*

#### [Added forRemoval=true to Previously Deprecated ContentSigner APIs](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8242260)

### Other notes

*client-libs*

#### [Workaround for Windows GDI API's memory restrictions](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8240654)

*client-libs/java.awt*

#### [java.awt.Robot.delay() Method Completes With Interrupt Status Set When Interrupted](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8210231)

*core-libs/java.io:serialization*

#### [Improved Serialization Handling](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8234836)

*core-libs/java.lang*

#### [Optimized Empty Substring Handling](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8240094)

*core-libs/java.lang.invoke*

#### [LookupdefineClass Links the Class](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8238195)

*core-libs/java.net*

#### [DatagramSocketdisconnect Allows an Implementation to Throw UncheckedIOException](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8235783)

#### [java.net.HttpClient Does Not Override Protocols Specified in SSLContext Default Parameters](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8239594)

#### [Filtering and Ordering of Addresses Returned by Alternative Hosts File Name Service Provider](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8244958)

#### [DatagramPacket.getPort() Returns 0 When the Port Is Not Set](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8237890)

*core-libs/java.nio.charsets*

#### [Modified the MS950 charset Encoder's Conversion Table](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8232161)

*core-libs/java.text*

#### [Support Monetary Grouping Separator in DecimalFormat/DecimalFormatSymbols](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8227313)

*core-libs/java.time*

#### [`localizedBy()` Overrides Localized Values With Default Values](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8244245)

#### [ValueRange.of(long, long, long) Does Not Throw IAE on Invalid Inputs](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8239520)

*core-libs/java.util.jar*

#### [Performance Improvement for InflaterOutputStream.write](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8242848)

*core-libs/java.util.regex*

#### [Incorrect behavior matching Unicode linebreaks](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8258259)

#### [Case Insensitive Matching Doesn't Work Correctly for Some Character Classes](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8214245)

*core-libs/java.util:collections*

#### [Better Listing of Arrays](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8231800)

#### [`TreeMap.computeIfAbsent` Mishandles Existing Entries Whose Values Are `null`](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8259622)

*core-libs/java.util:i18n*

#### [Support for CLDR version 37](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8239480)

#### [Localized Time Zone Name Inconsistency Between English and Other Locales](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8236548)

*tools/jpackage*

#### [[macos] Support for Notarizing jpackage app-image and dmg](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8237490)

*hotspot/compiler*

#### [Flags Controlling C1 Inlining Have New Name](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8235673)

*hotspot/gc*

#### [Improved Ergonomics for G1 Heap Region Size](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8241670)

#### [JEP 377 ZGC A Scalable Low-Latency Garbage Collector (Production)](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8209683)

#### [Disabling large pages on Windows](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8245000)

#### [Disabling NUMA Interleaving on Windows](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8245002)

*hotspot/runtime*

#### [Field Layout Computation Changed](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8237767)

#### [Enable ShowCodeDetailsInExceptionMessages by default](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8233014)

*security-libs/java.security*

#### [Signature and SignatureSpi Get Parameter Methods May Return null When Unsupported](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8243424)

*security-libs/javax.crypto:pkcs11*

#### [SunPKCS11 Initialization With NSS When External FIPS Modules Are in Security Modules Database](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8238555)

*security-libs/javax.net.ssl*

#### [Default SSLEngine Should Create in Server Role](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8237474)

*tools/javac*

#### [JEP 375 Pattern Matching for instanceof (Second Preview)](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8235186)

*tools/javadoc(tool)*

#### [Standard Doclet Index Files Compression](https://www.oracle.com/java/technologies/javase/15-relnote-issues.html#JDK-8237909)
