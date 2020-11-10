---
description: 'In this section, you will find information about a formula dependencies'
---

# Dependencies

## What are dependencies?

{% hint style="info" %}
Each programming language has its own specificities **to import libraries or packages**.
{% endhint %}

On Ritchie, it's possible to configure each formula as an independent and small project.

Therefore, it will be possible to import all the necessary dependencies to perform the operations you want to implement.

{% tabs %}
{% tab title="go.mod \(GOLANG\)" %}
```text
module formula

go 1.14

require (
    github.com/gookit/color v1.2.5
)
```
{% endtab %}

{% tab title="pom.xml \(JAVA\)" %}
```text
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>

    <groupId>com.ritchie</groupId>
    <artifactId>formula</artifactId>
    <version>1.0-SNAPSHOT</version>

    <properties>
        <java.version>1.8</java.version>
        <maven.compiler.source>${java.version}</maven.compiler.source>
        <maven.compiler.target>${java.version}</maven.compiler.target>
        <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
        <maven-jar-plugin.version>3.2.0</maven-jar-plugin.version>
    </properties>

    <build>
        <finalName>Main</finalName>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
            <plugin>
                <!-- Build an executable JAR -->
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-jar-plugin</artifactId>
                <version>${maven-jar-plugin.version}</version>
                <configuration>
                    <archive>
                        <manifest>
                            <!-- <addClasspath>true</addClasspath> -->
                            <mainClass>com.ritchie.Main</mainClass>
                        </manifest>
                    </archive>
                </configuration>
            </plugin>
            <plugin>
                <artifactId>maven-assembly-plugin</artifactId>
                <configuration>
                    <appendAssemblyId>false</appendAssemblyId>
                    <archive>
                        <manifest>
                            <mainClass>com.ritchie.Main</mainClass>
                        </manifest>
                    </archive>
                    <descriptorRefs>
                        <descriptorRef>jar-with-dependencies</descriptorRef>
                    </descriptorRefs>
                </configuration>
                <executions>
                    <execution>
                        <id>make-assembly</id>
                        <phase>package</phase>
                        <goals>
                            <goal>single</goal>
                        </goals>
                    </execution>
                </executions>
            </plugin>
        </plugins>
    </build>

    <dependencies>
        <dependency>
            <groupId>junit</groupId>
            <artifactId>junit</artifactId>
            <version>4.13.1</version>
            <scope>test</scope>
        </dependency>

        <dependency>
            <groupId>com.github.tomas-langer</groupId>
            <artifactId>chalk</artifactId>
            <version>1.0.2</version>
        </dependency>
    </dependencies>
</project>
```
{% endtab %}

{% tab title="package.json \(NODE\)" %}
```text
{
  "dependencies": {
    "cli-color": "^2.0.0"
  },
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "version": "1.0.0"
}
```
{% endtab %}

{% tab title="requirements.txt \(PYTHON\)" %}
```text
colored==1.4.2
```
{% endtab %}

{% tab title="composer.json \(PHP\)" %}
```text
{
  "require": {
    "codedungeon/php-cli-colors": "~1.0"
  }
}
```
{% endtab %}
{% endtabs %}



