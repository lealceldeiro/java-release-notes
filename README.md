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

### [Compact Profiles](https://docs.oracle.com/javase/8/docs/technotes/guides/compactprofiles/)

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
