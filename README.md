# qqwry-java

[![Build Status](https://drone.io/github.com/jarod/qqwry-java/status.png)](https://drone.io/github.com/jarod/qqwry-java/latest)

### usage:

Code sample:
```java
QQWry qqwry = new QQWry(); // load qqwry.dat from classpath

QQWry qqwry = new QQWry(Paths.get("path/to/qqwry.dat")); // load qqwry.dat from java.nio.file.Path

byte[] data = Files.readAllBytes(Paths.get("path/to/qqwry.dat"));
QQWry qqwry = new QQWry(data); // create QQWry with provided data

String myIP = "127.0.0.1";
IPZone ipzone = qqwry.findIP(myIP);
System.out.printf("%s, %s", ipzone.getMainInfo(), ipzone.getSubInfo());
// IANA, 保留地址用于本地回送
```

Gradle:
```groovy
dependencies {
   compile(
     "com.github.jarod:qqwry-java:0.6.2",
   )
}
```

Maven:
```xml
<dependency>
  <groupId>com.github.jarod</groupId>
  <artifactId>qqwry-java</artifactId>
  <version>0.6.2</version>
</dependency>
```

### build:

```
# OPTIONAL To embed qqwry.dat in the jar file, copy qqwry.dat to src/main/resources/qqwry.dat
# jar file will out put as ./build/lib/qqwry-java-X.X.X.jar
./gradlew jar
```
