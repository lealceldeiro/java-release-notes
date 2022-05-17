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

*core-libs/java.util:i18n*

[Square Character Support for Japanese New Era](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8211398)

*hotspot/gc*

[ZGC Concurrent Class Unloading](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8214897)

[Allocation of Old Generation of Java Heap on Alternate Memory Devices](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8202286)

*hotspot/runtime*

[HotSpot Windows OS Detection Correctly Identifies Windows Server 2019](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8211106)

[Command-Line Flag -XX+ExtensiveErrorReports](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8211845)

*security-libs/java.security*

[`disallow` and `allow` Options for `java.security.manager` System Property](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8191053)

[`-groupname` Option Added to keytool Key Pair Generation](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8213400)

For example, keytool `-genkeypair -keyalg EC -groupname secp384r1` will generate an `EC` key pair by using the `secp384r1` curve. Because there might be multiple curves with the same size, using the `-groupname` option is preferred over the `-keysize` option.

[New Java Flight Recorder (JFR) Security Events](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8148188)

These events are disabled by default and can be enabled via the JFR configuration files or via standard JFR options.

- `jdk.SecurityPropertyModification`
- `jdk.TLSHandshake`
- `jdk.X509Validation`
- `jdk.X509Certificate`

[Customizing PKCS12 keystore Generation](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8076190)

*security-libs/javax.net.ssl*

[ChaCha20 and Poly1305 TLS Cipher Suites](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8140466)

Refer to the "Java Secure Socket Extension (JSSE) Reference Guide" for details on these new TLS cipher suites. See (JDK-8140466](https://bugs.java.com/bugdatabase/view_bug.do?bug_id=JDK-8140466)

*security-libs/org.ietf.jgss:krb5*

[Support for dns_canonicalize_hostname in krb5.conf](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8210821)

The `dns_canonicalize_hostname` [flag](https://web.mit.edu/kerberos/krb5-devel/doc/admin/conf_files/krb5_conf.html) in the `krb5.conf` configuration file is now supported by the JDK Kerberos implementation. When set to `true`, a short hostname in a service principal name will be canonicalized to a fully qualified domain name if available. Otherwise, no canonicalization is performed. The default value is `true`.

*tools*

[`jdeps --print-module-deps` Reports Transitive Dependences](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8213909)

The `--no-recursive` option can be used to request non-transitive dependence analysis.

The `--ignore-missing-deps` option can be used to suppress missing dependence errors.

*tools/javac*

[JEP 325 Switch Expressions (Preview)](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8192963)

## Removed Features and Options

*client-libs/java.awt*

[Removal of com.sun.awt.SecurityWarning Class](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8210692)

*core-libs/java.io*

[Removal of `finalize` Methods from `FileInputStream` and `FileOutputStream`](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8192939)

*core-libs/java.util.jar*

[Removal of `finalize` Method in `java.util.ZipFile`/`Inflator`/`Deflator`](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8212129)

*infrastructure/build*

[Dropped the YY.M Vendor Version String from Oracle-Produced Builds](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8211726)

As of JDK 12, JDK builds from Oracle will no longer include a vendor version string

*security-libs/java.security*

[Removal of GTE CyberTrust Global Root](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8195793)

*tools/javac*

[Removal of `javac` Support for 6/1.6 source, target, and release Values](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8028563)

## Deprecated Features and Options

*hotspot/runtime*

[Obsoleted `-XX+`/`-MonitorInUseLists`](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8211384)

*security-libs/java.security*

[Deprecated Default Keytool `-keyalg` Value](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8212003)

## Other Notes

*client-libs/javax.swing*

[GTK+ 3.20 and Later Unsupported by Swing](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8218469)

*core-libs/java.lang*

[Initial Value of `user.timezone` System Property Changed](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8185496)

The initial value of the `user.timezone` system property is undefined unless set using a command line argument, for example, `-Duser.timezone="America/New_York"`. The first time the default timezone is needed, if `user.timezone` is undefined or empty the timezone provided by the operating system is used. Previously, the initial value was the empty string. In JDK 12, `System.getProperty("user.timezone")` may return null.

*core-libs/java.net*

[Better HTTP Redirection Support](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8196902)

[Changed `URLPermission` Behavior with Query or Fragments in URL String](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8213616)

*core-libs/java.time*

[Support New Japanese Era in `java.time.chrono.JapaneseEra`](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8212941)

*core-libs/java.util*

[Changed `Properties.loadFromXML` to Comply with Specification](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8213325)

*core-libs/javax.naming*

[LDAPS Communication Failure](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8211107)

*hotspot/gc*

[G1 May Uncommit Memory During Marking Cycle](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-6490394)

*hotspot/jvmti*

[`can_pop_frame` and `can_force_early_return` Capabilities are Disabled if JVMCI Compiler is Used](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8218025)

Being tracked here: https://bugs.java.com/bugdatabase/view_bug.do?bug_id=JDK-8218885

*infrastructure/build*

[Linux Native Code Checks](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8199552)

Additional safeguards to protect against buffer overruns in native code have been enabled on Linux. If a buffer overrun is encountered, the system will write the message "stack smashing detected" and the program will exit. Issues of this type should be reported to your vendor.

*security-libs/java.security*

[Added Additional TeliaSonera Root Certificate](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8210432)

[Removal of AOL and Swisscom Root Certificates](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8203230)

*security-libs/javax.crypto*

[Change to X25519 and X448 Encoded Private Key Format](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8213363)

*security-libs/javax.net.ssl*

[Removed TLS v1 and v1.1 from SSLContext Required Algorithms](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8214140)

[Disabled TLS anon and NULL Cipher Suites](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8211883)

[Disabled All DES TLS Cipher Suites](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8208350)

[Distrust TLS Server Certificates Anchored by Symantec Root CAs](https://www.oracle.com/java/technologies/javase/12-relnote-issues.html#JDK-8207258)
