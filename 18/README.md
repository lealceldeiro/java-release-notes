# [Java 18](https://docs.oracle.com/en/java/javase/18/) [Release Notes Documentation](https://www.oracle.com/java/technologies/javase/18-relnotes.html)

## [Release Notes](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html)

### New Features and Enhancements

*core-libs/java.nio.charsets*

#### [JEP 400: UTF-8 by Default](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8187041)

*core-libs/java.net*

[JEP 408: Simple Web Server](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8260510)

*core-libs/java.lang:reflect*

#### [JEP 416: Reimplement Core Reflection With Method Handles](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8271820)

*core-libs/java.net*

#### [JEP 418: Internet-Address Resolution SPI](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8263693)

**JEPs for Tool improvements:**

*tools/javadoc(tool)*

#### [JEP 413: Code Snippets in Java API Documentation](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8201533)

**JEPs for Previews and Incubators:**

*core-libs*

#### [JEP 417: Vector API (Third Incubator)](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8269306)

#### [JEP 419: Foreign Function & Memory API (Second Incubator)](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8274073)

*specification/language*

#### [JEP 420: Pattern Matching for switch (Second Preview)](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8273326)

*hotspot/gc*

#### [ZGC Supports String Deduplication](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8267186)

#### [SerialGC Supports String Deduplication](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8272609)

#### [ParallelGC Supports String Deduplication](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8267185)

*tools/javac*

#### [Passing Originating Elements From Filer to JavaFileManager](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8272234)

*core-libs/java.nio.charsets*

#### [Charset.forName() Taking fallback Default Value](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8270490)

*core-libs/java.util*

#### [New System Property to Control the Default Date Comment Written Out by java.util.Properties::store Methods](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8231640)

*core-libs/javax.annotation.processing*

#### [printError, printWarning, and printNote methods on Messager](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8273157)

*core-libs/javax.lang.model*

#### [Method to Get Outermost Type Element](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8140442)

#### [Map from an Element to its JavaFileObject](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8224922)

#### [Mapping between SourceVersion and Runtime.Version](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8275308)

*hotspot/compiler*

#### [Improve Compilation Replay](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8254106)

*hotspot/gc*

#### [Configurable Card Table Card Size](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8272773)

#### [Allow G1 Heap Regions up to 512MB](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8275056)

*hotspot/jfr*

#### [JDK Flight Recorder Event for Finalization](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8266936)

*security-libs*

#### [SunPKCS11 Provider Now Supports Some PKCS#11 v3.0 APIs](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8255409)

*security-libs/java.security*

#### [Alternate Subject.getSubject and doAs APIs Created That Do Not Depend on Security Manager APIs](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8267108)

#### [KeyStore Has a getAttributes Method](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8225181)

#### [Support for RSASSA-PSS in OCSP Response](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8274471)

#### [New Option -version Added to keytool and jarsigner Commands](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8272163)

#### [Migrate cacerts From JKS to Password-Less PKCS12](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8275252)

#### [Allow Store Password to Be Null When Saving a PKCS12 KeyStore](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8231107)

*security-libs/javax.crypto:pkcs11*

#### [SunPKCS11 Provider Supports AES Cipher With KW and KWP Modes if Supported by PKCS11 Library](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8264849)

*tools/javac*

#### [Expand checks of javac's serial lint warning](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8202056)

*tools/javadoc(tool)*

#### [Options to Include Script Files in Generated Documentation](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8275786)

#### [@SuppressWarnings for DocLint Messages](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8189591)

### Removed Features and Options

*security-libs/java.security*

#### [Removal of IdenTrust Root Certificate](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8225082)

#### [Removal of Google's GlobalSign Root Certificate](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8225083)

*client-libs/2d*

#### [Removal of Empty finalize() Methods in java.desktop Module](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8273102)

*core-libs/java.net*

#### [Removal of Support for Pre JDK 1.4 DatagramSocketImpl Implementations](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8260428)

#### [Removal of impl.prefix JDK System Property Usage From InetAddress](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8274227)

#### [Removal of Legacy PlainSocketImpl and PlainDatagramSocketImpl Implementations](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8253119)

*security-libs/org.ietf.jgss:krb5*

#### [Removal of default_checksum and safe_checksum_type From krb5.conf](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8274656)

### Deprecated Features and Options

**JEPs for Deprecation and Removals:**

*core-libs/java.lang*

#### [JEP 421: Deprecated Finalization for Removal](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8274609)

*security-libs/javax.security*

#### [Deprecated Subject::doAs for Removal](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8267108)

*core-libs*

#### [Deprecated sun.misc.Unsafe Methods That Return Offsets](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8277863)

*core-libs/java.lang*

#### [Terminally Deprecated Thread.stop](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8277861)

*hotspot/gc*

#### [Obsoleted Product Options -XX:G1RSetRegionEntries and -XX:G1RSetSparseRegionEntries](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8017163)

### Other notes
 
*install/install*

#### [Extended Delay Before JDK Executable Installer Starts From Network Drive](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8274002)

*security-libs/java.security*

#### [Change the java.security.manager System Property Default Value to disallow](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8270380)

#### [Disabled SHA-1 Signed JARs](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8269039)

*tools/javac*

#### [Enclosing Instance Fields Omitted from Inner Classes That Don't Use Them](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8271623)

#### [Corrected References to Overloaded Methods in Javadoc Documentation](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8278373)

*core-libs/java.io*

#### [Default charset for PrintWriter That Wraps PrintStream](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8276970)

*core-libs/java.io:serialization*

#### [ObjectInputStream.GetField.get(name, object) Throws ClassNotFoundException](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8276665)

To revert to the old behavior, a system property, `jdk.serialGetFieldCnfeReturnsNull`, has been added to the 
implementation. Setting the value to true reverts to the old behavior (returning `null`); leaving it unset or to any 
other value results in the throwing of `ClassNotFoundException`.

#### [Deserialization Filter and Filter Factory Property Error Reporting Were Under Specified](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8278087)

*core-libs/javax.naming*

#### [System Property to Control Reconstruction of Reference Address Objects by JDK's Built-in JNDI LDAP Implementation](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8267712)

*core-libs/java.net*

#### [HttpURLConnection's getHeaderFields and URLConnection.getRequestProperties Methods Return Field Values in the Order They Were Added](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8133686)

#### [Prohibit Null for Header Keys and Values in com.sun.net.httpserver.Headers](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8268960)

*core-libs/java.nio*

#### [ReadableByteChannel::read No Longer Throws ReadOnlyBufferException](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8275149)

#### [Zip File System Provider Throws ZipException When Entry Name Element Contains "." or ".."](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8251329)

*core-libs/java.time*

#### [Update Timezone Data to 2021c](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8274407)

*core-libs/java.util.jar*

#### [Disabled JAR Index Support](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8273401) 

#### [Closes Out Compressor When IOException Encountered While Using Default JDK Compressor in GZIPOutputStream.finish() , ZipOutputStream.closeEntry() and DeflaterOutputStream.close()](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8193682)

*hotspot/gc*

#### [ZGC: Fixed Long Process Non-Strong References Times](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8277212)

*security-libs/java.security*

#### [X509Certificate.get{Subject,Issuer}AlternativeNames and getExtendedKeyUsage Do Not Throw CertificateParsingException if Extension Is Unparseable](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8251468)

*security-libs/javax.crypto*

#### [Fix Issues With the KW and KWP Modes of SunJCE Provider](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8271745)

*security-libs/javax.net.ssl*

#### [Call X509KeyManager.chooseClientAlias Once for All Key Types](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8262186)

*security-libs/org.ietf.jgss:krb5*

#### [Removed Weak etypes From Default krb5 etype List](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8273670)

*tools/javac*

#### [Index Noteworthy Terms for jdk.compiler and jdk.javadoc Modules](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8278318)

*tools/javadoc(tool)*

#### [Improved Navigation on Small Devices](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8273034)

#### [DocLint Reports Missing Descriptions](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8272374)

#### [Updated Documentation for DocLint](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8275146)

#### [Indicate Invalid Input in Generated Output](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8276964)

#### [Merge "Exceptions" and "Errors" into "Exception Classes"](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8269401)

*core-libs/java.io*

#### [file.encoding System Property Has an Incorrect Value on Windows](https://www.oracle.com/java/technologies/javase/18-relnote-issues.html#JDK-8275145) 