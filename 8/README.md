# Java 8 Release - Notes

Oracle Release Notes: https://www.oracle.com/technetwork/java/javase/8-whats-new-2157071.html

### [Java Programming Language](https://docs.oracle.com/javase/8/docs/technotes/guides/language/enhancements.html#javase8)

* [Lambda Expressions](https://docs.oracle.com/javase/tutorial/java/javaOO/lambdaexpressions.html).
* [Method references](https://docs.oracle.com/javase/tutorial/java/javaOO/methodreferences.html).
* [Default methods](https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html).
* [Repeating Annotations](https://docs.oracle.com/javase/tutorial/java/annotations/repeating.html).
* [Type Annotations](https://docs.oracle.com/javase/tutorial/java/annotations/type_annotations.html).
* Improved [type inference](https://docs.oracle.com/javase/tutorial/java/generics/genTypeInference.html).
* [Method parameter reflection](https://docs.oracle.com/javase/tutorial/reflect/member/methodparameterreflection.html).

### [Collections](https://docs.oracle.com/javase/8/docs/technotes/guides/collections/changes8.html)

* [New and Enhanced APIs That Take Advantage of Lambda Expressions and Streams (`java.util.stream package`)](https://docs.oracle.com/javase/8/docs/technotes/guides/language/lambda_api_jdk8.html).
* Performance Improvement for HashMaps with Key Collisions.

### [Concurrency](https://docs.oracle.com/javase/8/docs/technotes/guides/concurrency/changes8.html)

* Classes and interfaces have been added to the `java.util.concurrent` package.
  - Interface [`CompletableFuture.AsynchronousCompletionTask`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletableFuture.AsynchronousCompletionTask.html): A marker interface identifying asynchronous tasks produced by async methods.
  - Interface [`CompletionStage<T>`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletionStage.html): A stage of a possibly asynchronous computation, that performs an action or computes a value when another `CompletionStage` completes.
  - Class [`CompletableFuture<T>`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletableFuture.html): A Future that may be explicitly completed (setting its value and status), and may be used as a `CompletionStage`, supporting dependent functions and actions that trigger upon its completion.
  - Class [`ConcurrentHashMap.KeySetView<K,V>`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.KeySetView.html): A view of a `ConcurrentHashMap` as a `Set` of keys, in which additions may optionally be enabled by mapping to a common value.
  - Class [`CountedCompleter<T>`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CountedCompleter.html): A `ForkJoinTask` with a completion action performed when triggered and there are no remaining pending actions.
  - Class [`CompletionException`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/CompletionException.html): Exception thrown when an error or other exception is encountered in the course of completing a result or task.
* Methods have been added to the [`java.util.concurrent.ConcurrentHashMap`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ConcurrentHashMap.html) class to support aggregate operations based on the newly added streams facility and lambda expressions.
* Classes have been added to the [`java.util.concurrent.atomic`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/atomic/package-summary.html) package to support scalable updatable variables.
* Methods have been added to the [`java.util.concurrent.ForkJoinPool`](https://docs.oracle.com/javase/8/docs/api/java/util/concurrent/ForkJoinPool.html) class to support a common pool.
* The [`java.util.concurrent.locks.StampedLock`](https://docs.oracle.com/javase/8/docs/api/index.html?java/util/concurrent/package-summary.html) class has been added to provide a capability-based lock with three modes for controlling read/write access.

### [Date-Time Package](https://docs.oracle.com/javase/8/docs/technotes/guides/datetime/index.html)

* [`java.time`](https://docs.oracle.com/javase/8/docs/api/java/time/package-summary.html) - Classes for date, time, date and time combined, time zones, instants, duration, and clocks.
* [`java.time.chrono`](https://docs.oracle.com/javase/8/docs/api/java/time/chrono/package-summary.html) - API for representing calendar systems other than ISO-8601. Several predefined chronologies are provided and you can also define your own chronology.
* [`java.time.format`](https://docs.oracle.com/javase/8/docs/api/java/time/format/package-summary.html) - Classes for formatting and parsing dates and time.
* [`java.time.temporal`](https://docs.oracle.com/javase/8/docs/api/java/time/temporal/package-summary.html) - Extended API, primarily for framework and library writers, allowing interoperations between the date and time classes, querying, and adjustment. Fields and units are defined in this package.
* [`java.time.zone`](https://docs.oracle.com/javase/8/docs/api/java/time/zone/package-summary.html) - Classes that support time zones, offsets from time zones, and time zone rules.
* JSR 310: Date and Time API

### [`java.lang and java.util Packages`](https://docs.oracle.com/javase/8/docs/technotes/guides/lang/enhancements.html#jdk8)

* Parallel Array Sorting
* Standard Encoding and Decoding Base64
* Unsigned Arithmetic Support

### [JDBC](https://docs.oracle.com/javase/8/docs/technotes/guides/jdbc/)

* The JDBC-ODBC Bridge has been removed.
* JDBC 4.2 introduces new features.

### Java DB

* JDK 8 includes Java DB 10.10.

### [Networking](https://docs.oracle.com/javase/8/docs/technotes/guides/net/enhancements-8.0.html)

* The class `java.net.URLPermission` has been added.
* In the class `java.net.HttpURLConnection`, if a security manager is installed, calls that request to open a connection require permission.

### [IO and NIO](https://docs.oracle.com/javase/8/docs/technotes/guides/io/enhancements.html#jdk8)

* New `SelectorProvider` implementation for Solaris based on the Solaris event port mechanism. To use, run with the system property `java.nio.channels.spi.Selector` set to the value `sun.nio.ch.EventPortSelectorProvider`.
* Decrease in the size of the `<JDK_HOME>/jre/lib/charsets.jar` file
* Performance improvement for the `java.lang.String(byte[], *)` constructor and the `java.lang.String.getBytes()` method.

### [Security](https://docs.oracle.com/javase/8/docs/technotes/guides/security/enhancements-8.html)

* Client-side TLS 1.2 enabled by default.
* New variant of AccessController.doPrivileged that enables code to assert a subset of its privileges, without preventing the full traversal of the stack to check for other permissions.
* Stronger algorithms for password-based encryption.
* SSL/TLS Server Name Indication (SNI) Extension support in JSSE Server.
* Support for AEAD algorithms.
* KeyStore enhancements.
* SHA-224 Message Digests.
* Enhanced Support for NSA Suite B Cryptography.
* Better Support for High Entropy Random Number Generation.
* New `java.security.cert.PKIXRevocationChecker` class for configuring revocation checking of X.509 certificates.
* 64-bit PKCS11 for Windows.
* New rcache Types in Kerberos 5 Replay Caching.
* Support for Kerberos 5 Protocol Transition and Constrained Delegation.
* Kerberos 5 weak encryption types disabled by default.
* Unbound SASL for the GSS-API/Kerberos 5 mechanism.
* SASL service for multiple host names.
* JNI bridge to native JGSS on Mac OS X.
* Support for stronger strength ephemeral DH keys in the SunJSSE provider.
* Support for server-side cipher suites preference customization in JSSE.

### [Tools](https://docs.oracle.com/javase/8/docs/technotes/tools/enhancements-8.html)

* The `jjs` command is provided to invoke the Nashorn engine.
* The `java` command launches JavaFX applications.
* The `java` man page has been reworked.
* The `jdeps` command-line tool is provided for analyzing class files.
* Java Management Extensions (JMX) provide remote access to diagnostic commands.
* The `jarsigner` tool has an option for requesting a signed time stamp from a Time Stamping Authority (TSA).
* [Javac tool](https://docs.oracle.com/javase/8/docs/technotes/guides/javac/index.html)
  - The `-parameters` option of the `javac` command can be used to store formal parameter names and enable the Reflection API to retrieve formal parameter names.
  - The type rules for equality operators in the Java Language Specification (JLS) Section 15.21 are now correctly enforced by the `javac` command.
  - The `javac` tool now has support for checking the content of `javadoc` comments for issues that could lead to various problems, such as invalid HTML or accessibility issues, in the files that are generated when `javadoc` is run. The feature is enabled by the new `-Xdoclint` option. For more details, see the output from running `javac -X`. This feature is also available in the `javadoc` tool, and is enabled there by default.
  - The `javac` tool now provides the ability to generate native headers, as needed. This removes the need to run the `javah` tool as a separate step in the build pipeline. The feature is enabled in `javac` by using the new `-h` option, which is used to specify a directory in which the header files should be written. Header files will be generated for any class which has either native methods, or constant fields annotated with a new annotation of type `java.lang.annotation.Native`.
* [Javadoc tool](https://docs.oracle.com/javase/8/docs/technotes/guides/javadoc/whatsnew-8.html)
  - The `javadoc` tool supports the new DocTree API that enables you to traverse Javadoc comments as abstract syntax trees.
  - The `javadoc` tool supports the new Javadoc Access API that enables you to invoke the Javadoc tool directly from a Java application, without executing a new process. See the `javadoc` what's new page for more information.
  - The `javadoc` tool now has support for checking the content of javadoc comments for issues that could lead to various problems, such as invalid HTML or accessibility issues, in the files that are generated when `javadoc` is run. The feature is enabled by default, and can also be controlled by the new `-Xdoclint` option. For more details, see the output from running `javadoc -X`. This feature is also available in the `javac` tool, although it is not enabled by default there.

### [Scripting](http://docs.oracle.com/javase/8/docs/technotes/guides/scripting/enhancements.html#jdk8)

* The *Rhino* javascript engine has been replaced with the [*Nashorn*](http://docs.oracle.com/javase/8/docs/technotes/guides/scripting/nashorn/) Javascript Engine.

### [Internationalization](https://docs.oracle.com/javase/8/docs/technotes/guides/intl/enhancements.8.html)

* Unicode Enhancements, including support for Unicode 6.2.0
* Adoption of Unicode CLDR Data and the java.locale.providers System Property
* New Calendar and Locale APIs
* Ability to Install a Custom Resource Bundle as an Extension

### [Deployment](https://docs.oracle.com/javase/8/docs/technotes/guides/jweb/enhancements-8.html)

* For sandbox applets and Java Web Start applications, URLPermission is now used to allow connections back to the server from which they were started. SocketPermission is no longer granted.
* The Permissions attribute is required in the JAR file manifest of the main JAR file at all security levels.

### [Compact Profiles](https://docs.oracle.com/javase/8/docs/technotes/guides/compactprofiles/)

### [Pack200](http://docs.oracle.com/javase/8/docs/technotes/guides/pack200/enhancements.html)

* Pack200 Support for Constant Pool Entries and New Bytecodes Introduced by JSR 292
* JDK8 support for class files changes specified by JSR-292, JSR-308 and JSR-335

### [JavaFX](https://docs.oracle.com/javase/8/javase-clienttechnologies.htm)

* The new [Modena](http://fxexperience.com/2013/03/modena-theme-update/) theme has been implemented in this release.
* The new `SwingNode` class enables developers to [embed Swing content into JavaFX applications](https://docs.oracle.com/javase/8/javafx/interoperability-tutorial/embed-swing.htm).
* The new UI Controls include the `DatePicker` and the `TreeTableView` controls.
* The [`javafx.print`](https://docs.oracle.com/javase/8/javafx/api/javafx/print/package-summary.html) package provides the public classes for the JavaFX Printing API.
* The [3D Graphics](https://docs.oracle.com/javase/8/javafx/graphics-tutorial/javafx-3d-graphics.htm) features now include 3D shapes, camera, lights, subscene, material, picking, and antialiasing. The new `Shape3D` (`Box`, `Cylinder`, `MeshView`, and `Sphere` subclasses), `SubScene`, `Material`, `PickResult`, `LightBase` (`AmbientLight` and `PointLight` subclasses), and `SceneAntialiasing` API classes have been added to the JavaFX 3D Graphics library. The `Camera` API class has also been updated in this release.
* The `WebView` class provides new features and improvements. Review [Supported Features of HTML5](https://docs.oracle.com/javase/8/javafx/embedded-browser-tutorial/index.html) for more information about additional HTML5 features including Web Sockets, Web Workers, and Web Fonts.
* Support for Hi-DPI displays has been added in this release.
* The CSS Styleable classes (`javafx.css javadoc`) became public API.
* The new `ScheduledService` class allows to automatically restart the service.
* JavaFX is now available for ARM platforms. JDK for ARM includes the base, graphics and controls components of JavaFX.
