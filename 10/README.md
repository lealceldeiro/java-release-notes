# [Java 10](https://docs.oracle.com/javase/10/) [Release Notes](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html)

## [What's New in JDK 10 - New Features and Enhancements](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html#NewFeature)

Also see [Java SE 10 (18.3) (JSR)](https://cr.openjdk.java.net/~iris/se/10/latestSpec/)

----

_core-libs/java.util_

**`Optional.orElseThrow()` Method**

A new method `orElseThrow` has been added to the `Optional` class. It is synonymous with and is now the preferred alternative to the existing `get` method.

_core-libs/java.util:collections_

**APIs for Creating Unmodifiable Collections** 

Several new APIs have been added that facilitate the creation of unmodifiable collections. The `List.copyOf`, `Set.copyOf`, and `Map.copyOf` methods create new collection instances from existing instances. New methods `toUnmodifiableList`, `toUnmodifiableSet`, and `toUnmodifiableMap` have been added to the `Collectors` class in the `Stream` package. These allow the elements of a Stream to be collected into an unmodifiable collection.

_core-svc/java.lang.management_

**System Property to Disable JRE Last Usage Tracking**

A new system property `jdk.disableLastUsageTracking` has been introduced to disable JRE last usage tracking for a running VM. This property can be set in the command line by using either `-Djdk.disableLastUsageTracking=true` or `-Djdk.disableLastUsageTracking`. With this system property set, JRE last usage tracking will be disabled regardless of the `com.oracle.usagetracker.track.last.usage` property value set in `usagetracker.properties`.

_core-svc/javax.management_

**Hashed Passwords for Out-of-the-Box JMX Agent**

The clear passwords present in the `jmxremote.password` file are now being over-written with their SHA3-512 hash by the JMX agent.

_hotspot/gc_

**JEP 307 Parallel Full GC for G1**

Improves G1 worst-case latencies by making the full GC parallel. The G1 garbage collector is designed to avoid full collections, but when the concurrent collections can't reclaim memory fast enough a fall back full GC will occur. The old implementation of the full GC for G1 used a single threaded mark-sweep-compact algorithm. With JEP 307 the full GC has been parallelized and now use the same amount of parallel worker threads as the young and mixed collections.

_security-libs/java.security_

**JEP 319 Root Certificates**

Provides a default set of root Certification Authority (CA) certificates in the JDK.

The `cacerts` keystore of the OpenJDK 9 binary for Linux x64 has been populated by [JEP 319: Root Certificates](http://openjdk.java.net/jeps/319) [<sup><sub>**https://bugs.java.com/bugdatabase/view_bug.do?bug_id=JDK-8191486**</sub></sup>] with a set of root certificates issued by the CAs of Oracle's Java SE Root CA Program. This addresses the problem of the empty cacerts keystore in the OpenJDK 9 binary for Linux x64. The empty cacerts keystore had prevented TLS connections from being established because Trusted Root Certificate Authorities were not installed. As a workaround for OpenJDK 9 binaries, users had to set the javax.net.ssl.trustStore System Property to use a different keystore.

_security-libs/javax.net.ssl_

**TLS Session Hash and Extended Master Secret Extension Support**

_tools/javac_

**Bytecode Generation for Enhanced for Loop**

Bytecode generation has been improved for enhanced for loops, providing an improvement in the translation approach for them. For example: `List<String> data = new ArrayList<>(); for (String b : data);`

The following is the code generated after the enhancement:
```
{ /*synthetic*/ Iterator i$ = data.iterator(); for (; i$.hasNext(); ) { String b = (String)i$.next(); } b = null; i$ = null; }
```

Declaring the iterator variable outside of the for loop allows a `null` to be assigned to it as soon as it is no longer used. This makes it accessible to the GC, which can then get rid of the unused memory. Something similar is done for the case when the expression in the enhanced for loop is an array.

_tools/[javadoc](https://docs.oracle.com/javase/10/tools/javadoc.htm#JSWOR-GUID-9D532574-1CDB-4D30-99F3-A308DCAEE55F)(tool)_

**`javadoc` Support for Multiple Stylesheets**

A new `javadoc` command-line option, `--add-stylesheet`, has been added to the javadoc tool. The new `--add-stylesheet` option provides support for the use of multiple stylesheets in the generated documentation. The existing `-stylesheetfile` option now has an alias, `--main-stylesheet`, to help distinguish the main stylesheet from any additional stylesheets.

**Overriding Methods That Do Not Change the Specification**

A new option `--overridden-methods=value`, has been added to the `javadoc` tool. Many classes override inherited methods without changing the specification. The `--overridden-methods=value` option can be used to group these methods with other inherited methods, instead of documenting them in detail with the other methods declared in the class.

**Comment Tag for Summary of an API Description**

A new inline tag, `{@summary ...}`, has been added to explicitly specify the text used as the summary of the API description. By default, the summary of an API description is inferred from the first sentence. This is determined by using either a simple algorithm or `java.text.BreakIterator`. However, the heuristics for this are not always correct and can lead to an incorrect determination of the end of the first sentence. The new tag enables the API summary text to be explicitly set instead of inferred. More info at [Documentation Comment Specification for the Standard Doclet[(http://docs.oracle.com/javase/10/docs/specs/doc-comment-spec.html).

## [Removed Features and Options](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html#Removed)

More into at [Java SE 10 (18.3) (JSR 383)](http://cr.openjdk.java.net/~iris/se/10/latestSpec/).

_client-libs_

**Removal of Support for Using Old LookAndFeel**

It is no longer possible for applications to use old or unsupported LookAndFeels. Some applications (such as, Nimbus and Aqua) used old class names to instantiate JDK internal Swing LookAndFeels. These classes were internal to the JDK and applications should have always treated them as such. Applications that use these class names to instantiate JDK internal Swing LookAndFeels must migrate now.

_core-libs/java.lang_

**Removal of `Runtime.getLocalizedInputStream` and `getLocalizedOutputStream` Methods**

The methods `Runtime.getLocalizedInputStream` and `Runtime.getLocalizedOutputStream` have been removed. They were part of an obsolete internationalization mechanism and have no known uses.

_core-libs/java.rmi_

**Removal of RMI Server-Side Multiplex Protocol Support**

The RMI Multiplex protocol was disabled in JDK 9 and has been removed.

_deploy/plugin_

**Removal of Common DOM APIs**

The `com.sun.java.browser.plugin2.DOM`, and `sun.plugin.dom.DOMObject` APIs have been removed. Applications can use `netscape.javascript.JSObject` to manipulate the DOM.

_hotspot/runtime_

**Removal of FlatProfiler**

The FlatProfiler, deprecated in JDK 9, has been made obsolete by removing the implementation code. The FlatProfiler was enabled by setting the `-Xprof` VM argument. The `-Xprof` flag remains recognized in this release; however, setting it will print out a warning message.

**Removal of Obsolete `-X` Options**

The obsolete HotSpot VM options (`-Xoss`, `-Xsqnopause`, `-Xoptimize`, `-Xboundthreads`, and `-Xusealtsigs`) have been removed.

_javafx/application-lifecycle_

**Removal of HostServicesgetWebContext Method**

The `HostServices::getWebContext` method, which was deprecated for removal in JDK 9, has been removed. There is no replacement for this functionality. Applications will no longer be able to communicate with the enclosing web page of a JavaFX Applet. The Java Plug-in, on which this functionality depends, is deprecated for removal as well.

_javafx/graphics_

**Removal of T2K Rasterizer and ICU Layout Engine From JavaFX**

The T2K rasterizer and ICU layout engine have been removed from JavaFX.

_javafx/media_

**Removal of Deprecated VP6/FXM/FLV Code From JavaFX**

Support for VP6 video encoding format and FXM/FLV container has been removed in JavaFX Media. Users are encouraged to use H.264/AVC1 in the MP4 container or HTTP Live Streaming instead.

_security-libs/java.security_

**Removal of Deprecated Pre-1.2 SecurityManager Methods and Fields**

The following pre-1.2 deprecated `java.lang.SecurityManager` methods and fields that were marked _`forRemoval=true`_ have been removed:

* `inCheck` field
* `getInCheck` method
* `classDepth` method
* `classLoaderDepth` method
* `currentClassLoader` method
* `currentLoadedClass` method
* `inClass` method
* `inClassLoader` method

In addition, the deprecated `checkMemberAccess` method has been changed to throw a `SecurityException` if the caller has not been granted `AllPermission`. This method is error-prone and users should instead invoke the `checkPermission` method directly.

_security-libs/javax.security_

**Removal of Deprecated Classes in `com.sun.security.auth.**`**

The following deprecated classes that were marked for removal in JDK 9 have been removed:

* `com.sun.security.auth.PolicyFile`
* `com.sun.security.auth.SolarisNumericGroupPrincipal`
* `com.sun.security.auth.SolarisNumericUserPrincipal`
* `com.sun.security.auth.SolarisPrincipal`
* `com.sun.security.auth.X500Principal`
* `com.sun.security.auth.module.SolarisLoginModule`
* `com.sun.security.auth.module.SolarisSystem`

_tools/javadoc(tool)_

**Removal of Old (JDK 6, JDK 7, and JDK 8 Era) Standard Doclet**

The old (JDK 6, JDK 7 and JDK 8 era) standard doclet, which outputs HTML content, and which has been superseded by a replacement, has been removed in this release. The underlying javadoc API (see `com.sun.javadoc` in the API documentation) has been deprecated, but is still available for the time being, for use by user-provided doclets.

_tools/javah_

**JEP 313 Remove the Native-Header Generation Tool (`javah`)**

As previously announced, the native-header tool, `javah`, has been removed.

Native headers can now be generated by using the Java compiler, `javac`, with the `-h` option.

_tools/launcher_

**Removal of Java Launcher's Data Model Options -d32 and -d64**

The java launcher's data model selection options (-d32, -d64, -J-d32 and -J-d64) have been removed. They are obsolete and were previously deprecated. To prevent the launcher from failing, users must remove usages of these options when invoking the `java` launcher or tools such as `javac` and `javah`.

## [Deprecated Features and Options](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html#Deprecated)

More info at [Deprecated API page (API specification)](http://cr.openjdk.java.net/~iris/se/10/latestSpec/api/deprecated-list.html), [Java SE 10 (18.3) (JSR 383)](http://cr.openjdk.java.net/~iris/se/10/latestSpec/) and [Compatibility & Specification Review (CSR)](https://wiki.openjdk.java.net/display/csr/Main).

_core-svc/javax.management_

**SNMP Monitoring Support Deprecated forRemoval**

The `jdk.snmp` module that provides the [SNMP monitoring and management support for the Java virtual machine](https://docs.oracle.com/javase/10/management/snmp-monitoring-and-management.htm#JSMGM-GUID-D6FA8012-625C-4412-986F-867896F89696) has been deprecated and is planned to be removed in a future release.

A warning message for deprecation is emitted when JVM SNMP monitoring is enabled (via the `com.sun.management.snmp.port` property configured in the `management.properties` configuration file).

_security-libs/java.security_

**`java.security.{Certificate,Identity,IdentityScope,Signer}` APIs Deprecated forRemoval**

The deprecated `java.security.{Certificate, Identity, IdentityScope, Signer}` classes have been marked _`forRemoval=true`_ and are subject to removal in a future version of Java SE.

**`java.security.acl` APIs Deprecated `forRemoval`**

The deprecated `java.security.acl` APIs have been marked _`forRemoval=true`_ and are subject to removal in a future version of Java SE.

_security-libs/javax.security_

**`javax.security.auth.Policy` API Deprecated `forRemoval`**

The deprecated `javax.security.auth.Policy` class has been marked _`forRemoval=true`_ and will be removed in a future release. The `javax.security.auth.Policy` class has been deprecated since JDK 1.4 and superseded or replaced by `java.security.Policy`.

## [Other Notes](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html#Remaining)

## [Compatibility & Specification Review (CSR)](https://wiki.openjdk.java.net/display/csr/Main)

## [Books](https://docs.oracle.com/javase/10/javase-docs.htm)
