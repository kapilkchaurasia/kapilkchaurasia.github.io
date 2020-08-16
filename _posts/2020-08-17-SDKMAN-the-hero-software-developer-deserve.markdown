---
layout: post
title: "SDKMAN! The hero software developer deverse"
date: 2020-08-17 13:27:18 +0800
categories: sdk-manager
---
# **SDKMAN!** 
#### Its a tool for managing parallel versions of multiple Software Development Kits on most Unix based systems. 
#### It provides a convenient Command Line Interface (CLI) and API for installing, switching, removing and listing Candidates. Formerly known as GVM the Groovy enVironment Manager, it was inspired by the very useful [RVM](https://rvm.io/) and [rbenv](https://github.com/rbenv/rbenv) tools  


## Features!

  - **Lightweight**
    Written in bash and only requires curl and zip/unzip to be present on your system. Even works with ZSH too.
  - **Multi-platform**
    Runs on any UNIX based platforms: Mac OSX, Linux, Cygwin, Solaris and FreeBSD.
   - **By Developers, for Developers**
     Making life easier. No more trawling download pages, extracting archives, messing with _HOME and PATH environment variables.
   - **Java all the way down**
     Install Software Development Kits for the JVM such as Java, Groovy, Scala, Kotlin and Ceylon. Ant, Gradle, Grails, Maven, SBT, Spark, Spring Boot, Vert.x and many others also supported.

## Usage

### **Installing an SDK**
### Latest Stable
Install the latest stable version of your SDK of choice (say, Java JDK) by running the following command:
```sh
$ sdk install java
```
You will see something like the following output:
 ```sh                               
Downloading: java 8u111

In progress...

######################################################################## 100.0%

Installing: java 8u111
Done installing!
```
Now you will be prompted if you want this version to be set as **default**.
```sh
Do you want java 8u111 to be set as default? (Y/n):
Answering yes (or hitting enter) will ensure that all subsequent shells opened will have this version of the SDK in use by default.
Setting java 8u111 as default.
```

### Specific Version
Need a specific version of an SDK? Simply qualify the version you require:
```sh
$ sdk install scala 2.12.1
```
All subsequent steps same as above.

### Install Local Version(s)
Using a snapshot version? Already have a local installation? Setup a local version by specifying the path to the local installation:
```sh
$ sdk install groovy 3.0.0-SNAPSHOT /path/to/groovy-3.0.0-SNAPSHOT
$ sdk install java 10-zulu /Library/Java/JavaVirtualMachines/zulu-10.jdk/Contents/Home
```
Note that the local version name (3.0.0-SNAPSHOT and 10-zulu in the examples above) must be a unique name which is not already in the list of available version names.

### **Remove Version**
Remove an installed version.
```sh
$ sdk uninstall scala 2.11.6
```
Note that removing a local version will not remove the local installation.

### **List Candidates**
To get a listing of available Candidates:
```sh
$ sdk list
This will render a searchable alphabetic list with name, current stable default version, website URL, description and easy install command for each Candidate. The output is piped to less so standard keyboard shortcuts may be used with q to exit.

================================================================================
Available Candidates
================================================================================
q-quit                                  /-search down
j-down                                  ?-search up
k-up                                    h-help
--------------------------------------------------------------------------------
Groovy (2.4.5)                                       http://www.groovy-lang.org/

Groovy is a powerful, optionally typed and dynamic language, with static-typing
and static compilation capabilities, for the Java platform aimed at multiplying
developers’ productivity thanks to a concise, familiar and easy to learn syntax.
It integrates smoothly with any Java program, and immediately delivers to your
application powerful features, including scripting capabilities, Domain-Specific
Language authoring, runtime and compile-time meta-programming and functional
programming.

                                        $ sdk install groovy
--------------------------------------------------------------------------------
Scala (2.11.7)                                        http://www.scala-lang.org/
...
```

### **List Versions**
To get a listing of Candidate Versions:
```sh
$ sdk list groovy
This will result in a list view showing the available, local, installed and current versions of the SDK.

================================================================================
Available Groovy Versions
================================================================================
> * 2.4.4                2.3.1                2.0.8                1.8.3
2.4.3                2.3.0                2.0.7                1.8.2
2.4.2                2.2.2                2.0.6                1.8.1
2.4.1                2.2.1                2.0.5                1.8.0
2.4.0                2.2.0                2.0.4                1.7.9
2.3.9                2.1.9                2.0.3                1.7.8
2.3.8                2.1.8                2.0.2                1.7.7
2.3.7                2.1.7                2.0.1                1.7.6
2.3.6                2.1.6                2.0.0                1.7.5
2.3.5                2.1.5                1.8.9                1.7.4
2.3.4                2.1.4                1.8.8                1.7.3
2.3.3                2.1.3                1.8.7                1.7.2
2.3.2                2.1.2                1.8.6                1.7.11
2.3.11               2.1.1                1.8.5                1.7.10
2.3.10               2.1.0                1.8.4                1.7.1

================================================================================
+ - local version
* - installed
> - currently in use
================================================================================
```

### **Use Version**
Choose to use a given version in the current terminal:
```sh
$ sdk use scala 2.12.1
```
It is important to realise that this will switch the candidate version for the current shell only. To make this change permanent, use the default command instead.

### **Default Version**
Chose to make a given version the default:
```sh
$ sdk default scala 2.11.6
```
This will ensure that all subsequent shells will start with version 2.11.6 in use.

### **Current Version(s)**
To see what is currently in use for a Candidate:
```sh
$ sdk current java
```
