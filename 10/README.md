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

[1] https://bugs.java.com/view_bug.do?bug_id=JDK-8191486

## [Removed Features and Options](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html#Removed)

## [Deprecated Features and Options](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html#Deprecated)

## [Other Notes](https://www.oracle.com/technetwork/java/javase/10-relnote-issues-4108729.html#Remaining)

## [Compatibility & Specification Review (CSR)](https://wiki.openjdk.java.net/display/csr/Main)

## [Books](https://docs.oracle.com/javase/10/javase-docs.htm)
