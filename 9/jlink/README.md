# `jlink` <sup><sub>[The Java Module System][1]</sub></sup>

It’s a Java command-line tool (in your JDK’s bin folder) that you can use to select a number of platform modules and link them into a runtime image. Such a runtime image acts exactly like a JRE but contains only the modules you picked and the dependencies they need to function (as indicated by `requires` directives). During that linking phase, `jlink` can be used to further optimize image size and improve VM performance, particularly startup time.

`jlink` can also create application images, which include app code as well as library and framework modules. This allows your build process to produce an entirely self-contained deployment unit that consists of your entire app with exactly the platform modules it needs, optimized for image size and performance as you see fit, and launchable with a simple call to a native script.

> Note: jlink “just” links bytecode—it doesn’t compile it to machine code

### Required info for jlink to create an image, specified with a command-line option:

* Where to find the available modules (specified with `--module-path`)
* Which modules to use (specified with `--add-modules`)
* Folder in which to create the image (specified with `--output`)

**Example:**

```shell
$ jlink
    --module-path ${jdk-9}/jmods    # Location of modules, in this case platform modules from the local JDK install  
    --add-modules java.base         # Modules to add to the image, in this case only java.base
    --output jdk-base               # Output directory for the image
$ jdk-base/bin/java --list-modules  # Executes java --list-modules from the new image to verify that it only contains the base module 

> java.base
```

> Note: From Java 10 on, it’s no longer necessary to place platform modules on the module path. If it doesn’t contain any, `jlink` implicitly loads them from the directory `$JAVA_HOME/jmods`.

The created custom image contains the following directories:

* `bin`: binaries like `java`, `javac` and `jlink`
* `conf`: configuration files like `.properties`, `.policy` and others
* `include`: C header files
* `legal`
* `lib`: all modules fused into a single file, native libraries (i.e.: `.ddd` and `.so` files) and others (`.properties`, `.policy`)
* `release`


`jlink`, by default, performs no service binding when creating an image. Instead, service-provider modules have to be included manually by listing them in `--add-modules`. Alternatively, the option `--bind-services` can be used to include all modules that provide a service that’s used by another resolved module.

[1]: https://www.amazon.com/dp/1617294284/ref=cm_sw_em_r_mt_dp_U_WXX8Eb6J2XEDV
