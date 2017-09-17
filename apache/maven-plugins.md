[Source](http://maven.apache.org/plugins/index.html "Permalink to Maven – Available Plugins")

# Maven – Available Plugins

## Available Plugins

Maven is - at its heart - a plugin execution framework; all work is done by plugins. Looking for a specific goal to execute? This page lists the core plugins and others. There are the build and the reporting plugins:
* **Build plugins** will be executed during the build and they should be configured in the `<build>` element from the POM.
* **Reporting plugins** will be executed during the site generation and they should be configured in the `<reporting>` element from the POM. Because the result of a Reporting plugin is part of the generated site, Reporting plugins should be both internationalized and localized. You can read more about the [localization of our plugins][52] and how you can help.

### Supported By The Maven Project

To see the most up-to-date list browse the Maven repository, specifically the [ `org/apache/maven/plugins`][53] subfolder. _(Plugins are organized according to a directory structure that resembles the standard Java package naming convention)_

|  **Plugin** |  **Type*** |  **Version** |  **Release Date** |  **Description** |  **Source Repository** |  **Issue Tracking** |  
| ----- | ----- | ----- | ----- | ----- | ----- |
|  **Core plugins** |   |   |   |  **Plugins corresponding to default core phases (ie. clean, compile). They may have multiple goals as well.** |   |   |  
|  [ `clean`][54] |  B |  3.0.0 |  2015-10-22 |  Clean up after the build. |  [SVN][55] |  [JIRA][56] |  
|  [ `compiler`][57] |  B |  3.7.0 |  2017-09-04 |  Compiles Java sources. |  [SVN][58] |  [JIRA][59] |  
|  [ `deploy`][60] |  B |  2.8.2 |  2014-08-27 |  Deploy the built artifact to the remote repository. |  [SVN][61] |  [JIRA][62] |  
|  [ `failsafe`][63] |  B |  2.20.1 |  2017-09-15 |  Run the JUnit integration tests in an isolated classloader. |  [GIT][64] |  [JIRA][65] |  
|  [ `install`][66] |  B |  2.5.2 |  2014-08-27 |  Install the built artifact into the local repository. |  [SVN][67] |  [JIRA][68] |  
|  [ `resources`][69] |  B |  3.0.2 |  2016-12-10 |  Copy the resources to the output directory for including in the JAR. |  [SVN][70] |  [JIRA][71] |  
|  [ `site`][72] |  B |  3.6 |  2016-11-17 |  Generate a site for the current project. |  [SVN][73] |  [JIRA][74] |  
|  [ `surefire`][75] |  B |  2.20.1 |  2017-09-15 |  Run the JUnit unit tests in an isolated classloader. |  [GIT][64] |  [JIRA][65] |  
|  [ `verifier`][76] |  B |  1.1 |  2015-04-14 |  Useful for integration tests - verifies the existence of certain conditions. |  [SVN][77] |  [JIRA][78] |  
|  **Packaging types/tools** |   |   |   |  **These plugins relate to packaging respective artifact types.** |   |   |  
|  [ `ear`][79] |  B |  2.10.1 |  2015-06-27 |  Generate an EAR from the current project. |  [SVN][80] |  [JIRA][81] |  
|  [ `ejb`][82] |  B |  3.0.0 |  2017-08-13 |  Build an EJB (and optional client) from the current project. |  [SVN][83] |  [JIRA][84] |  
|  [ `jar`][85] |  B |  3.0.2 |  2016-06-18 |  Build a JAR from the current project. |  [SVN][86] |  [JIRA][87] |  
|  [ `rar`][88] |  B |  2.4 |  2014-09-08 |  Build a RAR from the current project. |  [SVN][89] |  [JIRA][90] |  
|  [ `war`][91] |  B |  3.1.0 |  2017-04-26 |  Build a WAR from the current project. |  [SVN][92] |  [JIRA][93] |  
|  [ `app-client/acr`][94] |  B |  3.0.0 |  2015-01-23 |  Build a JavaEE application client from the current project. |  [SVN][95] |  [JIRA][96] |  
|  [ `shade`][97] |  B |  3.1.0 |  2017-08-22 |  Build an Uber-JAR from the current project, including dependencies. |  [SVN][98] |  [JIRA][99] |  
|  [ `source`][100] |  B |  3.0.1 |  2016-06-18 |  Build a source-JAR from the current project. |  [SVN][101] |  [JIRA][102] |  
|  **Reporting plugins** |   |   |   |  **Plugins which generate reports, are configured as reports in the POM and run under the site generation lifecycle.** |   |   |  
|  [ `changelog`][103] |  R |  2.3 |  2014-06-24 |  Generate a list of recent changes from your SCM. |  [SVN][104] |  [JIRA][105] |  
|  [ `changes`][106] |  B+R |  2.12.1 |  2016-11-01 |  Generate a report from an issue tracker or a change document. |  [SVN][107] |  [JIRA][108] |  
|  [ `checkstyle`][109] |  B+R |  2.17 |  2015-10-15 |  Generate a Checkstyle report. |  [SVN][110] |  [JIRA][111] |  
|  [ `doap`][112] |  B |  1.2 |  2015-03-17 |  Generate a Description of a Project (DOAP) file from a POM. |  [SVN][113] |  [JIRA][114] |  
|  [ `docck`][115] |  B |  1.1 |  2015-04-03 |  Documentation checker plugin. |  [SVN][116] |  [JIRA][117] |  
|  [ `javadoc`][118] |  B+R |  3.0.0-M1 |  2017-07-21 |  Generate Javadoc for the project. |  [SVN][119] |  [JIRA][120] |  
|  [ `jdeps`][121] |  B |  3.1.0 |  2017-09-02 |  Run JDK's JDeps tool on the project. |  [SVN][122] |  [JIRA][123] |  
|  [ `jxr`][124] |  R |  2.5 |  2014-11-02 |  Generate a source cross reference. |  [SVN][125] |  [JIRA][126] |  
|  [ `linkcheck`][127] |  R |  1.2 |  2014-10-08 |  Generate a Linkcheck report of your project's documentation. |  [SVN][128] |  [JIRA][129] |  
|  [ `pmd`][130] |  B+R |  3.8 |  2017-05-05 |  Generate a PMD report. |  [SVN][131] |  [JIRA][132] |  
|  [ `project-info-reports`][133] |  R |  2.9 |  2016-03-01 |  Generate standard project reports. |  [SVN][134] |  [JIRA][135] |  
|  [ `surefire-report`][136] |  R |  2.20.1 |  2017-09-15 |  Generate a report based on the results of unit tests. |  [GIT][64] |  [JIRA][65] |  
|  **Tools** |   |   |   |  **These are miscellaneous tools available through Maven by default.** |   |   |  
|  [ `ant`][137] |  B |  2.4 |  2014-12-15 |  Generate an Ant build file for the project. |  [SVN][138] |  [JIRA][139] |  
|  [ `antrun`][140] |  B |  1.8 |  2014-12-26 |  Run a set of ant tasks from a phase of the build. |  [SVN][141] |  [JIRA][142] |  
|  [ `archetype`][143] |  B |  3.0.1 |  2017-04-11 |  Generate a skeleton project structure from an archetype. |  [GIT][144] |  [JIRA][145] |  
|  [ `assembly`][146] |  B |  3.1.0 |  2017-08-13 |  Build an assembly (distribution) of sources and/or binaries. |  [SVN][147] |  [JIRA][148] |  
|  [ `dependency`][149] |  B+R |  3.0.1 |  2017-05-11 |  Dependency manipulation (copy, unpack) and analysis. |  [SVN][150] |  [JIRA][151] |  
|  [ `enforcer`][152] |  B |  3.0.0-M1 |  2017-07-30 |  Environmental constraint checking (Maven Version, JDK etc), User Custom Rule Execution. |  [SVN][153] |  [JIRA][154] |  
|  [ `gpg`][155] |  B |  1.6 |  2015-01-19 |  Create signatures for the artifacts and poms. |  [SVN][156] |  [JIRA][157] |  
|  [ `help`][158] |  B |  2.2 |  2013-02-23 |  Get information about the working environment for the project. |  [SVN][159] |  [JIRA][160] |  
|  [ `invoker`][161] |  B+R |  3.0.1 |  2017-07-21 |  Run a set of Maven projects and verify the output. |  [SVN][162] |  [JIRA][163] |  
|  [ `jarsigner`][164] |  B |  1.4 |  2015-01-21 |  Signs or verifies project artifacts. |  [SVN][165] |  [JIRA][166] |  
|  [ `patch`][167] |  B |  1.2 |  2015-03-09 |  Use the gnu patch tool to apply patch files to source code. |  [SVN][168] |  [JIRA][169] |  
|  [ `pdf`][170] |  B |  1.3 |  2015-02-16 |  Generate a PDF version of your project's documentation. |  [SVN][171] |  [JIRA][172] |  
|  [ `plugin`][173] |  B+R |  3.5 |  2016-08-30 |  Create a Maven plugin descriptor for any mojos found in the source tree, to include in the JAR. |  [SVN][174] |  [JIRA][175] |  
|  [ `release`][176] |  B |  2.5.3 |  2015-10-17 |  Release the current project - updating the POM and tagging in the SCM. |  [SVN][177] |  [JIRA][178] |  
|  [ `remote-resources`][179] |  B |  1.5 |  2013-08-14 |  Copy remote resources to the output directory for inclusion in the artifact. |  [SVN][180] |  [JIRA][181] |  
|  [ `repository`][182] |  B |  2.4 |  2015-02-22 |  Plugin to help with repository-based tasks. |  [SVN][183] |  [JIRA][184] |  
|  [ `scm`][185] |  B |  1.9.5 |  2016-07-01 |  Execute SCM commands for the current project. |  [GIT][186] |  [JIRA][187] |  
|  [ `scm-publish`][188] |  B |  1.1 |  2014-05-18 |  Publish your Maven website to a scm location. |  [SVN][189] |  [JIRA][190] |  
|  [ `stage`][191] |  B |  1.0 |  2015-03-03 |  Assists with release staging and promotion. |  [SVN][192] |  [JIRA][193] |  
|  [ `toolchains`][194] |  B |  1.1 |  2014-11-12 |  Allows to share configuration across plugins. |  [SVN][195] |  [JIRA][196] |

* **B**uild or **R**eporting plugin

There are also some sandbox plugins into our [source repository][197].

Previous archived versions of plugins reference documentations are [located here][198].

### Retired


|  **Plugin** |  **Type*** |  **Version** |  **Retired Date** |  **Description** |  
| ----- |----- |----- |----- |
|  [ `eclipse`][199] |  B |  2.10 |  2015-10-07 |  Generate an Eclipse project files for the current project. |  
|  [ `idea`][200] |  B |  2.2.1 |  2013-07-26 |  Create/update an IDEA workspace for the current project (individual modules are created as IDEA modules) |  
|  [ `one`][201] |  B |  1.3 |  2013-07-30 |  A plugin for interacting with legacy Maven 1.x repositories and builds. |  
|  [ `reactor`][202] |  B |  1.1 |  2014-03-24 |  Build a subset of interdependent projects in a reactor (Maven 2 only). |

### Outside The Maven Land

#### At codehaus.org

`Due to the shutdown of codehaus.org [all plugins are under transition][203] to the new location. This means that currently some of the links might be invalid. We are continiously cleaning up the links.`

There are also [many plug-ins][204] available at the [ MojoHaus][205] project at GitHub.

Here are a few common ones:

|  **Plugin** (see [complete list with version][204]) |  **Description** |  
| ----- |----- |
|  [ `animal-sniffer`][206] |  Build signatures of APIs (JDK for example) and checks your classes against them. |  
|  [ `build-helper`][207] |  Attach extra artifacts and source folders to build. |  
|  [ `castor`][208] |  Generate sources from an XSD using Castor. |  
|  [ `clirr`][209] |  Compare binaries or sources for compatibility using Clirr |  
|  [ `javacc`][210] |  Generate sources from a JavaCC grammar. |  
|  [ `jdepend`][211] |  Generate a report on code metrics using JDepend. |  
|  [ `nar-maven-plugin`][212] |  Compiles C, C++, Fortran for different architectures. |  
|  [ `native`][213] |  Compiles C and C++ code with native compilers. |  
|  [ `sql`][214] |  Executes SQL scripts from files or inline. |  
|  [ `taglist`][215] |  Generate a list of tasks based on tags in your code. |  
|  [ `versions`][216] |  Manage versions of your project, its modules, dependencies and plugins. |

#### At code.google.com

There are also [many plug-ins][217] available at the [ Google Code][218].

#### Misc

A number of other projects provide their own Maven plugins. This includes:

|  **Plugin** |  **Maintainer** |  **Description** |  
|----- |----- |----- |
|  [ `cargo`][219] |  [Cargo Project][219] |  Start/stop/configure J2EE containers and deploy to them. |  
|  [ `clover`][220] |  [Atlassian Clover][221] |  Generate a Clover report. |  
|  [ `jetty`][222] |  [Jetty Project][223] |  Jetty Run a Jetty container for rapid webapp development. |  
|  [ `jalopy`][224] |  [Triemax][225] |  Use Jalopy to format your source code. |  
|  [ `rat`][226] |  [Apache Creadur Project][227] |  Release Audit Tool (RAT) to verify files. |  
|  [ `Genesis Plugins`][228] |  [Apache Geronimo Project][229] |  Verify legal files in artifacts. |  
|  [ `Apache Tomcat`][230] |  [Apache Tomcat Project][230] |  Run an Apache Tomcat container for rapid webapp development. |

### Resources

1. [Guide to Configuring Plugins][231]

* * *

Copyright ©2002–2017 [The Apache Software Foundation][232]. All rights reserved.

[1]: http://maven.apache.org/images/apache-maven-project.png
[2]: http://maven.apache.org/images/maven-logo-black-on-white.png
[3]: https://www.apache.org/ "Apache"
[4]: http://maven.apache.org/index.html "Maven"
[5]: http://maven.apache.org/index.html "Welcome"
[6]: https://www.apache.org/licenses/ "License"
[7]: http://maven.apache.org/download.html "Download"
[8]: http://maven.apache.org/install.html "Install"
[9]: http://maven.apache.org/configure.html "Configure"
[10]: http://maven.apache.org/run.html "Run"
[11]: http://maven.apache.org/ide.html "IDE Integration"
[12]: http://maven.apache.org/what-is-maven.html "What is Maven?"
[13]: http://maven.apache.org/maven-features.html "Features"
[14]: http://maven.apache.org/general.html "FAQ"
[15]: http://maven.apache.org/support-and-training.html "Support and Training"
[16]: http://maven.apache.org#
[17]: http://maven.apache.org/guides/index.html "Index (category)"
[18]: http://maven.apache.org/run-maven/index.html "Running Maven"
[19]: http://maven.apache.org/users/index.html "User Centre"
[20]: http://maven.apache.org/plugin-developers/index.html "Plugin Developer Centre"
[21]: http://maven.apache.org/repository/index.html "Maven Central Repository"
[22]: http://maven.apache.org/developers/index.html "Maven Developer Centre"
[23]: http://maven.apache.org/articles.html "Books and Resources"
[24]: http://maven.apache.org/security.html "Security"
[25]: http://maven.apache.org/community.html "Community Overview"
[26]: http://maven.apache.org/guides/development/guide-helping.html "How to Contribute"
[27]: http://maven.apache.org/guides/mini/guide-maven-evangelism.html "Maven Repository"
[28]: http://maven.apache.org/users/getting-help.html "Getting Help"
[29]: http://maven.apache.org/issue-tracking.html "Issue Tracking"
[30]: http://maven.apache.org/source-repository.html "Source Repository"
[31]: http://maven.apache.org/team-list.html "The Maven Team"
[32]: http://maven.apache.org/project-info.html "Project Information"
[33]: http://maven.apache.org/archetype/index.html "Archetype"
[34]: http://maven.apache.org/resolver/index.html "Artifact Resolver"
[35]: http://maven.apache.org/doxia/index.html "Doxia"
[36]: http://maven.apache.org/jxr/index.html "JXR"
[37]: http://maven.apache.org/ref/current "Maven"
[38]: http://maven.apache.org/pom/index.html "Parent POMs"
[39]: http://maven.apache.org/plugin-testing/index.html "Plugin Testing"
[40]: http://maven.apache.org/plugin-tools/index.html "Plugin Tools"
[41]: http://maven.apache.org/apache-resource-bundles/index.html "Resource Bundles"
[42]: http://maven.apache.org/scm/index.html "SCM"
[43]: http://maven.apache.org/shared/index.html "Shared Components"
[44]: http://maven.apache.org/skins/index.html "Skins"
[45]: http://maven.apache.org/surefire/index.html "Surefire"
[46]: http://maven.apache.org/wagon/index.html "Wagon"
[47]: https://www.apache.org/foundation/how-it-works.html "How Apache Works"
[48]: https://www.apache.org/foundation/ "Foundation"
[49]: https://www.apache.org/foundation/sponsorship.html "Sponsoring Apache"
[50]: https://www.apache.org/foundation/thanks.html "Thanks"
[51]: http://maven.apache.org/images/logos/maven-feather.png
[52]: http://maven.apache.org/localization.html
[53]: https://repo.maven.apache.org/maven2/org/apache/maven/plugins/
[54]: http://maven.apache.org/plugins/maven-clean-plugin/
[55]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-clean-plugin
[56]: https://issues.apache.org/jira/browse/MCLEAN
[57]: http://maven.apache.org/plugins/maven-compiler-plugin/
[58]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-compiler-plugin
[59]: https://issues.apache.org/jira/browse/MCOMPILER
[60]: http://maven.apache.org/plugins/maven-deploy-plugin/
[61]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-deploy-plugin
[62]: https://issues.apache.org/jira/browse/MDEPLOY
[63]: http://maven.apache.org/surefire/maven-failsafe-plugin/
[64]: https://git-wip-us.apache.org/repos/asf/maven-surefire.git
[65]: https://issues.apache.org/jira/browse/SUREFIRE
[66]: http://maven.apache.org/plugins/maven-install-plugin/
[67]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-install-plugin
[68]: https://issues.apache.org/jira/browse/MINSTALL
[69]: http://maven.apache.org/plugins/maven-resources-plugin/
[70]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-resources-plugin
[71]: https://issues.apache.org/jira/browse/MRESOURCES
[72]: http://maven.apache.org/plugins/maven-site-plugin/
[73]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-site-plugin/
[74]: https://issues.apache.org/jira/browse/MSITE
[75]: http://maven.apache.org/surefire/maven-surefire-plugin/
[76]: http://maven.apache.org/plugins/maven-verifier-plugin/
[77]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-verifier-plugin
[78]: https://issues.apache.org/jira/browse/MVERIFIER
[79]: http://maven.apache.org/plugins/maven-ear-plugin/
[80]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-ear-plugin
[81]: https://issues.apache.org/jira/browse/MEAR
[82]: http://maven.apache.org/plugins/maven-ejb-plugin/
[83]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-ejb-plugin
[84]: https://issues.apache.org/jira/browse/MEJB
[85]: http://maven.apache.org/plugins/maven-jar-plugin/
[86]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-jar-plugin
[87]: https://issues.apache.org/jira/browse/MJAR
[88]: http://maven.apache.org/plugins/maven-rar-plugin/
[89]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-rar-plugin
[90]: https://issues.apache.org/jira/browse/MRAR
[91]: http://maven.apache.org/plugins/maven-war-plugin/
[92]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-war-plugin
[93]: https://issues.apache.org/jira/browse/MWAR
[94]: http://maven.apache.org/plugins/maven-acr-plugin/
[95]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-acr-plugin
[96]: https://issues.apache.org/jira/browse/MACR
[97]: http://maven.apache.org/plugins/maven-shade-plugin/
[98]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-shade-plugin
[99]: https://issues.apache.org/jira/browse/MSHADE
[100]: http://maven.apache.org/plugins/maven-source-plugin/
[101]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-source-plugin
[102]: https://issues.apache.org/jira/browse/MSOURCES
[103]: http://maven.apache.org/plugins/maven-changelog-plugin/
[104]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-changelog-plugin
[105]: https://issues.apache.org/jira/browse/MCHANGELOG
[106]: http://maven.apache.org/plugins/maven-changes-plugin/
[107]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-changes-plugin
[108]: https://issues.apache.org/jira/browse/MCHANGES
[109]: http://maven.apache.org/plugins/maven-checkstyle-plugin/
[110]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-checkstyle-plugin
[111]: https://issues.apache.org/jira/browse/MCHECKSTYLE
[112]: http://maven.apache.org/plugins/maven-doap-plugin/
[113]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-doap-plugin
[114]: https://issues.apache.org/jira/browse/MDOAP
[115]: http://maven.apache.org/plugins/maven-docck-plugin/
[116]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-docck-plugin
[117]: https://issues.apache.org/jira/browse/MDOCCK
[118]: http://maven.apache.org/plugins/maven-javadoc-plugin/
[119]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-javadoc-plugin
[120]: https://issues.apache.org/jira/browse/MJAVADOC
[121]: http://maven.apache.org/plugins/maven-jdeps-plugin/
[122]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-jdeps-plugin
[123]: https://issues.apache.org/jira/browse/MJDEPS
[124]: http://maven.apache.org/jxr/maven-jxr-plugin/
[125]: https://svn.apache.org/repos/asf/maven/jxr/trunk/maven-jxr-plugin
[126]: https://issues.apache.org/jira/browse/JXR
[127]: http://maven.apache.org/plugins/maven-linkcheck-plugin/
[128]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-linkcheck-plugin
[129]: https://issues.apache.org/jira/browse/MLINKCHECK
[130]: http://maven.apache.org/plugins/maven-pmd-plugin/
[131]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-pmd-plugin
[132]: https://issues.apache.org/jira/browse/MPMD
[133]: http://maven.apache.org/plugins/maven-project-info-reports-plugin/
[134]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-project-info-reports-plugin
[135]: https://issues.apache.org/jira/browse/MPIR
[136]: http://maven.apache.org/surefire/maven-surefire-report-plugin/
[137]: http://maven.apache.org/plugins/maven-ant-plugin/
[138]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-ant-plugin
[139]: https://issues.apache.org/jira/browse/MANT
[140]: http://maven.apache.org/plugins/maven-antrun-plugin/
[141]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-antrun-plugin
[142]: https://issues.apache.org/jira/browse/MANTRUN
[143]: http://maven.apache.org/archetype/maven-archetype-plugin/
[144]: https://git-wip-us.apache.org/repos/asf/maven-archetype.git
[145]: https://issues.apache.org/jira/browse/ARCHETYPE
[146]: http://maven.apache.org/plugins/maven-assembly-plugin/
[147]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-assembly-plugin
[148]: https://issues.apache.org/jira/browse/MASSEMBLY
[149]: http://maven.apache.org/plugins/maven-dependency-plugin/
[150]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-dependency-plugin
[151]: https://issues.apache.org/jira/browse/MDEP
[152]: http://maven.apache.org/enforcer/maven-enforcer-plugin/
[153]: https://svn.apache.org/repos/asf/maven/enforcer/trunk/maven-enforcer-plugin
[154]: https://issues.apache.org/jira/browse/MENFORCER
[155]: http://maven.apache.org/plugins/maven-gpg-plugin/
[156]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-gpg-plugin
[157]: https://issues.apache.org/jira/browse/MGPG
[158]: http://maven.apache.org/plugins/maven-help-plugin/
[159]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-help-plugin
[160]: https://issues.apache.org/jira/browse/MPH
[161]: http://maven.apache.org/plugins/maven-invoker-plugin/
[162]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-invoker-plugin
[163]: https://issues.apache.org/jira/browse/MINVOKER
[164]: http://maven.apache.org/plugins/maven-jarsigner-plugin/
[165]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-jarsigner-plugin
[166]: https://issues.apache.org/jira/browse/MJARSIGNER
[167]: http://maven.apache.org/plugins/maven-patch-plugin/
[168]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-patch-plugin
[169]: https://issues.apache.org/jira/browse/MPATCH
[170]: http://maven.apache.org/plugins/maven-pdf-plugin/
[171]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-pdf-plugin
[172]: https://issues.apache.org/jira/browse/MPDF
[173]: http://maven.apache.org/plugin-tools/maven-plugin-plugin/
[174]: https://svn.apache.org/repos/asf/maven/plugin-tools/trunk/maven-plugin-plugin
[175]: https://issues.apache.org/jira/browse/MPLUGIN
[176]: http://maven.apache.org/plugins/maven-release-plugin/
[177]: https://svn.apache.org/repos/asf/maven/release/trunk/maven-release-plugin
[178]: https://issues.apache.org/jira/browse/MRELEASE
[179]: http://maven.apache.org/plugins/maven-remote-resources-plugin/
[180]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-remote-resources-plugin
[181]: https://issues.apache.org/jira/browse/MRRESOURCES
[182]: http://maven.apache.org/plugins/maven-repository-plugin/
[183]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-repository-plugin
[184]: https://issues.apache.org/jira/browse/MREPOSITORY
[185]: http://maven.apache.org/scm/maven-scm-plugin/
[186]: https://git-wip-us.apache.org/repos/asf/maven-scm.git
[187]: https://issues.apache.org/jira/browse/SCM
[188]: http://maven.apache.org/plugins/maven-scm-publish-plugin/
[189]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-scm-publish-plugin/
[190]: https://issues.apache.org/jira/browse/MSCMPUB
[191]: http://maven.apache.org/plugins/maven-stage-plugin/
[192]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-stage-plugin
[193]: https://issues.apache.org/jira/browse/MSTAGE
[194]: http://maven.apache.org/plugins/maven-toolchains-plugin/
[195]: https://svn.apache.org/repos/asf/maven/plugins/trunk/maven-toolchains-plugin
[196]: https://issues.apache.org/jira/browse/MTOOLCHAINS
[197]: https://svn.apache.org/repos/asf/maven/sandbox/trunk/plugins
[198]: http://maven.apache.org/plugins-archives/
[199]: http://maven.apache.org/plugins/maven-eclipse-plugin/
[200]: http://maven.apache.org/plugins/maven-idea-plugin/
[201]: http://maven.apache.org/plugins/maven-one-plugin/
[202]: http://maven.apache.org/plugins/maven-reactor-plugin/
[203]: http://www.mojohaus.org/
[204]: http://www.mojohaus.org/plugins.html
[205]: https://github.com/mojohaus
[206]: http://mojo.codehaus.org/animal-sniffer-maven-plugin/
[207]: http://www.mojohaus.org/build-helper-maven-plugin/
[208]: http://www.mojohaus.org/castor-maven-plugin/
[209]: http://www.mojohaus.org/clirr-maven-plugin/
[210]: http://mojo.codehaus.org/javacc-maven-plugin/
[211]: http://www.mojohaus.org/jdepend-maven-plugin/
[212]: http://maven-nar.github.io/
[213]: http://www.mojohaus.org/maven-native/native-maven-plugin/
[214]: http://www.mojohaus.org/sql-maven-plugin/
[215]: http://www.mojohaus.org/taglist-maven-plugin/
[216]: http://www.mojohaus.org/versions-maven-plugin/
[217]: https://code.google.com/hosting/search?q=maven+plugin+label%3Amaven&amp;projectsearch=Search+Projects
[218]: https://code.google.com
[219]: https://codehaus-cargo.github.io/
[220]: https://confluence.atlassian.com/display/CLOVER/Clover-for-Maven+2
[221]: https://www.atlassian.com/software/clover/
[222]: https://www.eclipse.org/jetty/documentation/current/jetty-maven-plugin.html
[223]: https://www.eclipse.org/jetty/
[224]: http://www.triemax.com/products/jalopy/manual/plugin-maven.html
[225]: http://www.triemax.com/
[226]: https://creadur.apache.org/rat/
[227]: https://creadur.apache.org/
[228]: https://geronimo.apache.org/maven/genesis/plugins/tools-maven-plugin/index.html
[229]: https://geronimo.apache.org/
[230]: https://tomcat.apache.org/maven-plugin.html
[231]: http://maven.apache.org/guides/mini/guide-configuring-plugins.html
[232]: https://www.apache.org/

  </reporting></build>
