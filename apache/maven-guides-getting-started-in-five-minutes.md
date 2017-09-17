
[Source](https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html "Permalink to Maven – Maven in 5 Minutes")

# Maven – Maven in 5 Minutes

## Maven in 5 Minutes

### Prerequisites

You must have an understanding of how to install software on your computer. If you do not know how to do this, please ask someone at your office, school, etc or pay someone to explain this to you. The Maven mailing lists are not the best place to ask for this advice.

### Installation

_Maven is a Java tool, so you must have [Java][57] installed in order to proceed._

First, [download Maven][58] and follow the [installation instructions][59]. After that, type the following in a terminal or in a command prompt:


    mvn --version

It should print out your installed version of Maven, for example:


    Apache Maven 3.0.5 (r01de14724cdef164cd33c7c8c2fe155faf9602da; 2013-02-19 14:51:28+0100)
    Maven home: D:apache-maven-3.0.5bin..
    Java version: 1.6.0_25, vendor: Sun Microsystems Inc.
    Java home: C:Program FilesJavajdk1.6.0_25jre
    Default locale: nl_NL, platform encoding: Cp1252
    OS name: "windows 7", version: "6.1", arch: "amd64", family: "windows"

Depending upon your network setup, you may require extra configuration. Check out the [Guide to Configuring Maven][60] if necessary.

**If you are using Windows, you should look at** [Windows Prerequisites][61] **to ensure that you are prepared to use Maven on Windows.**

### Creating a Project

You will need somewhere for your project to reside, create a directory somewhere and start a shell in that directory. On your command line, execute the following Maven goal:


    mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false

_If you have just installed Maven, it may take a while on the first run. This is because Maven is downloading the most recent artifacts (plugin jars and other files) into your local repository. You may also need to execute the command a couple of times before it succeeds. This is because the remote server may time out before your downloads are complete. Don't worry, there are ways to fix that._

You will notice that the _generate_ goal created a directory with the same name given as the artifactId. Change into that directory.


    cd my-app

Under this directory you will notice the following [standard project structure][62].


    my-app
    |-- pom.xml
    `-- src
        |-- main
        |   `-- java
        |       `-- com
        |           `-- mycompany
        |               `-- app
        |                   `-- App.java
        `-- test
            `-- java
                `-- com
                    `-- mycompany
                        `-- app
                            `-- AppTest.java

The `src/main/java` directory contains the project source code, the `src/test/java` directory contains the test source, and the `pom.xml` file is the project's Project Object Model, or POM.

#### The POM

The `pom.xml` file is the core of a project's configuration in Maven. It is a single configuration file that contains the majority of information required to build a project in just the way you want. The POM is huge and can be daunting in its complexity, but it is not necessary to understand all of the intricacies just yet to use it effectively. This project's POM is:


    <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemalocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
      <modelversion>4.0.0</modelversion>

      <groupid>com.mycompany.app</groupid>
      <artifactid>my-app</artifactid>
      <version>1.0-SNAPSHOT</version>
      <packaging>jar</packaging>

      <name>Maven Quick Start Archetype</name>
      <url>http://maven.apache.org</url>

      <dependencies>
        <dependency>
          <groupid>junit</groupid>
          <artifactid>junit</artifactid>
          <version>4.8.2</version>
          <scope>test</scope>
        </dependency>
      </dependencies>
    </project>

#### What did I just do?

You executed the Maven goal _archetype:generate_, and passed in various parameters to that goal. The prefix _archetype_ is the [plugin][63] that contains the goal. If you are familiar with [Ant][64], you may conceive of this as similar to a task. This goal created a simple project based upon an archetype. Suffice it to say for now that a _plugin_ is a collection of _goals_ with a general common purpose. For example the jboss-maven-plugin, whose purpose is "deal with various jboss items".

#### Build the Project


    mvn package

The command line will print out various actions, and end with the following:


     ...
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESSFUL
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time: 2 seconds
    [INFO] Finished at: Thu Jul 07 21:34:52 CEST 2011
    [INFO] Final Memory: 3M/6M
    [INFO] ------------------------------------------------------------------------

Unlike the first command executed (_archetype:generate_) you may notice the second is simply a single word - _package_. Rather than a goal, this is a _phase_. A phase is a step in the [build lifecycle][65], which is an ordered sequence of phases. When a phase is given, Maven will execute every phase in the sequence up to and including the one defined. For example, if we execute the _compile_ phase, the phases that actually get executed are:

1. validate
2. generate-sources
3. process-sources
4. generate-resources
5. process-resources
6. compile

You may test the newly compiled and packaged JAR with the following command:


    java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App

Which will print the quintessential:


    Hello World!

### Running Maven Tools

#### Maven Phases

Although hardly a comprehensive list, these are the most common _default_ lifecycle phases executed.

* **validate**: validate the project is correct and all necessary information is available
* **compile**: compile the source code of the project
* **test**: test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed
* **package**: take the compiled code and package it in its distributable format, such as a JAR.
* **integration-test**: process and deploy the package if necessary into an environment where integration tests can be run
* **verify**: run any checks to verify the package is valid and meets quality criteria
* **install**: install the package into the local repository, for use as a dependency in other projects locally
* **deploy**: done in an integration or release environment, copies the final package to the remote repository for sharing with other developers and projects.

There are two other Maven lifecycles of note beyond the _default_ list above. They are

* **clean**: cleans up artifacts created by prior builds
* **site**: generates site documentation for this project

Phases are actually mapped to underlying goals. The specific goals executed per phase is dependant upon the packaging type of the project. For example, _package_ executes _jar:jar_ if the project type is a JAR, and _war:war_ if the project type is - you guessed it - a WAR.

An interesting thing to note is that phases and goals may be executed in sequence.


    mvn clean dependency:copy-dependencies package

This command will clean the project, copy dependencies, and package the project (executing all phases up to _package_, of course).

#### Generating the Site


    mvn site

This phase generates a site based upon information on the project's pom. You can look at the documentation generated under `target/site`.

### Conclusion

We hope this quick overview has piqued your interest in the versatility of Maven. Note that this is a very truncated quick-start guide. Now you are ready for more comprehensive details concerning the actions you have just performed. Check out the [Maven Getting Started Guide][66].

* * *

Copyright ©2002–2017 [The Apache Software Foundation][67]. All rights reserved.

[1]: https://maven.apache.org/images/apache-maven-project.png
[2]: https://maven.apache.org/images/maven-logo-black-on-white.png
[3]: https://www.apache.org/ "Apache"
[4]: https://maven.apache.org/index.html "Maven"
[5]: https://maven.apache.org/index.html "Welcome"
[6]: https://www.apache.org/licenses/ "License"
[7]: https://maven.apache.org/download.html "Download"
[8]: https://maven.apache.org/install.html "Install"
[9]: https://maven.apache.org/configure.html "Configure"
[10]: https://maven.apache.org/run.html "Run"
[11]: https://maven.apache.org/ide.html "IDE Integration"
[12]: https://maven.apache.org/what-is-maven.html "What is Maven?"
[13]: https://maven.apache.org/maven-features.html "Features"
[14]: https://maven.apache.org/general.html "FAQ"
[15]: https://maven.apache.org/support-and-training.html "Support and Training"
[16]: https://maven.apache.org/plugins/index.html "Maven Plugins"
[17]: https://maven.apache.org/guides/index.html "Index (category)"
[18]: https://maven.apache.org/run-maven/index.html "Running Maven"
[19]: https://maven.apache.org/users/index.html "User Centre"
[20]: https://maven.apache.org#
[21]: https://maven.apache.org/guides/getting-started/index.html "Getting Started Guide"
[22]: https://maven.apache.org/users/getting-help.html "Getting Help"
[23]: https://maven.apache.org/settings.html "Settings Reference"
[24]: https://maven.apache.org/pom.html "POM Reference"
[25]: https://maven.apache.org/plugin-developers/index.html "Plugin Developer Centre"
[26]: https://maven.apache.org/repository/index.html "Maven Central Repository"
[27]: https://maven.apache.org/developers/index.html "Maven Developer Centre"
[28]: https://maven.apache.org/articles.html "Books and Resources"
[29]: https://maven.apache.org/security.html "Security"
[30]: https://maven.apache.org/community.html "Community Overview"
[31]: https://maven.apache.org/guides/development/guide-helping.html "How to Contribute"
[32]: https://maven.apache.org/guides/mini/guide-maven-evangelism.html "Maven Repository"
[33]: https://maven.apache.org/issue-tracking.html "Issue Tracking"
[34]: https://maven.apache.org/source-repository.html "Source Repository"
[35]: https://maven.apache.org/team-list.html "The Maven Team"
[36]: https://maven.apache.org/project-info.html "Project Information"
[37]: https://maven.apache.org/archetype/index.html "Archetype"
[38]: https://maven.apache.org/resolver/index.html "Artifact Resolver"
[39]: https://maven.apache.org/doxia/index.html "Doxia"
[40]: https://maven.apache.org/jxr/index.html "JXR"
[41]: https://maven.apache.org/ref/current "Maven"
[42]: https://maven.apache.org/pom/index.html "Parent POMs"
[43]: https://maven.apache.org/plugins/index.html "Plugins"
[44]: https://maven.apache.org/plugin-testing/index.html "Plugin Testing"
[45]: https://maven.apache.org/plugin-tools/index.html "Plugin Tools"
[46]: https://maven.apache.org/apache-resource-bundles/index.html "Resource Bundles"
[47]: https://maven.apache.org/scm/index.html "SCM"
[48]: https://maven.apache.org/shared/index.html "Shared Components"
[49]: https://maven.apache.org/skins/index.html "Skins"
[50]: https://maven.apache.org/surefire/index.html "Surefire"
[51]: https://maven.apache.org/wagon/index.html "Wagon"
[52]: https://www.apache.org/foundation/how-it-works.html "How Apache Works"
[53]: https://www.apache.org/foundation/ "Foundation"
[54]: https://www.apache.org/foundation/sponsorship.html "Sponsoring Apache"
[55]: https://www.apache.org/foundation/thanks.html "Thanks"
[56]: https://maven.apache.org/images/logos/maven-feather.png
[57]: http://www.oracle.com/technetwork/java/javase/downloads/index.html
[58]: https://maven.apache.org/download.html
[59]: https://maven.apache.org/download.html#Installation
[60]: https://maven.apache.org/mini/guide-configuring-maven.html
[61]: https://maven.apache.org/windows-prerequisites.html
[62]: https://maven.apache.org/introduction/introduction-to-the-standard-directory-layout.html
[63]: https://maven.apache.org/plugins/index.html
[64]: http://ant.apache.org
[65]: https://maven.apache.org/introduction/introduction-to-the-lifecycle.html
[66]: https://maven.apache.org/index.html
[67]: https://www.apache.org/
