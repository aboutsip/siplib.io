---
title: Get Started
layout: info
menu: getstarted.html
active_element: getstarted
---

<h1 id="getting-started">Getting Started</h1>

siplib is just a java library and is available through [Maven Central](http://search.maven.org/) and we will be using [Maven](http://maven.apache.org/) in these examples. If you are new to Maven, then check out [Maven: The Complete Reference](http://books.sonatype.com/mvnref-book/reference/), which should have you up and running in no time. If you are using any other build tools, their setup is usually quite similar so should not be hard to adopt the example below to fit your needs.

<h3 id="getting-started-maven">Setting up Maven</h3>

First, add a property to your POM with the current version of pkts.io, which is {{ site.pktsio_version }} (remember, siplib is part of pkts.io):

``` xml
<properties>
    <pktsio.version>{{ site.pktsio_version }}</pktsio.version>
</properties>
```

Add the pkts-sip library as a dependency:

``` xml
<dependencies>
    <dependency>
        <groupId>io.pkts</groupId>
        <artifactId>pkts-sip</artifactId>
        <version>${pktsio.version}</version>
    </dependency>
</dependencies>
```

<h3 id="getting-started-java-8">Configure for Java 8</h3>

pkts.io, and therefore siplib, requires Java 8 so you need to configure your Maven setup to use Java 8. To do this, you need to configure your compiler, which in Maven is accomplished by re-configuring the `maven-compiler-plugin` like so:

```xml
    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.1</version>
                <!-- compile for Java 1.8 -->
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                    <encoding>UTF-8</encoding>
                </configuration>
            </plugin>
        </plugins>
    </build>
```


Your final pom.xml should look like something like the following [gist](https://gist.github.com/aboutsip/286c89688d488185df09)

<h3 id="getting-started-examples">Examples</h3>

Now that we have Maven setup we are ready to start coding. You can either continue reading in the [docs](/docs) section, which will explain the philosphy behind siplib, how lambda functions are used and show some of the common use cases, or you can just checkout the [examples repository](https://github.com/aboutsip/pkts/tree/master/pkts-examples/src/main/java/io/pkts/examples/siplib) or even the [junit tests](https://github.com/aboutsip/pkts/tree/master/pkts-sip/src/test/java/io/pkts/packet/sip) if you really want to see the raw usage of siplib.

<h3 id="getting-started-javadoc">Javadoc</h3>
Javadocs for all releases are hosted by our friends at [javadoc.io](www.javadoc.io) and the current release of pkts.io (and as such siplib) is accessed through the following links:

 * [siplib](http://www.javadoc.io/doc/io.pkts/pkts-sip/{{page.pktsio_version}})

<h3 id="getting-started-contributing">Javadoc</h3>
Contributions are more than welcome and highly encouraged. Everything in siplib are following the general guidelines of Maven so if you are familiar with Maven you should have no problem getting started. Since siplib is part of pkts.io, please head over to that project site for a fuller description of how you can [contribute](http://www.aboutsip.com/pktsio/#contributing).

<h1 id="license">License</h1>
pkts.io and all projects under aboutsip.com are released under the terms of the <a href="http://en.wikipedia.org/wiki/MIT_License">MIT license

