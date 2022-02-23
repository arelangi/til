# Java Issues


Find out the java version

`java -version`

Find all versions of Java that are installed on your machine

`/usr/libexec/java_home -V`

and you will see something like 

```
Matching Java Virtual Machines (4):
    17.0.1 (x86_64) "Oracle Corporation" - "OpenJDK 17.0.1" /Users/aditya.relangi/Library/Java/JavaVirtualMachines/openjdk-17.0.1/Contents/Home
    1.8.321.07 (x86_64) "Oracle Corporation" - "Java" /Library/Internet Plug-Ins/JavaAppletPlugin.plugin/Contents/Home
    1.8.0_321 (x86_64) "Oracle Corporation" - "Java SE 8" /Library/Java/JavaVirtualMachines/jdk1.8.0_321.jdk/Contents/Home
    1.8.0_312 (x86_64) "Amazon" - "Amazon Corretto 8" /Users/aditya.relangi/Library/Java/JavaVirtualMachines/corretto-1.8.0_312/Contents/Home
```

Pick the version you want to be the default (1.6.0_65-b14-462 for arguments sake) then:

```
export JAVA_HOME=`/usr/libexec/java_home -v 1.8.0_312`
```

or you can specify just the major version, like:

```
export JAVA_HOME=`/usr/libexec/java_home -v 1.8`
```

Now when you run `java -version` you will see:

```
java version "1.6.0_65"
Java(TM) SE Runtime Environment (build 1.6.0_65-b14-462-11M4609)
Java HotSpot(TM) 64-Bit Server VM (build 20.65-b04-462, mixed mode)
```

Add the export `JAVA_HOME` line to your shell’s init file.

For Bash (as stated by antonyh):

`export JAVA_HOME=$(/usr/libexec/java_home -v 1.8)`