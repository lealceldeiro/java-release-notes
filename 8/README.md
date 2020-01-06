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

### [Compact Profiles](https://docs.oracle.com/javase/8/docs/technotes/guides/compactprofiles/)

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
