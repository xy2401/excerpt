[来源]（http://maven.apache.org/plugins/index.html“永久链接到Maven - 可用插件”）

# Maven - 可用的插件

## 可用的插件

Maven是其核心 - 一个插件执行框架;所有的工作都是通过插件完成的。寻找执行的具体目标？该页面列出了核心插件和其他插件。有build和报告插件：
* **构建插件** 将在构建期间执行，并且它们应该在POM中的`<build>`元素中配置。
* **报告插件** 将在站点生成期间执行，并且应在POM的`<reporting>`元素中配置。因为Reporting插件的结果是生成的站点的一部分，所以Reporting插件应该被国际化和本地化。您可以阅读更多关于[本地化我们的插件][52]以及如何帮助。

### 由Maven项目支持

要查看最新的列表，请浏览Maven存储库，特别是[`org / apache / maven / plugins`][53]子文件夹。_（插件根据类似于标准Java包命名约定的目录结构进行组织）_

| **插件** | **类型*** | **版本** | **发布日期** | **说明** | **源库** | **问题跟踪** |
| ----- | ----- | ----- | ----- | ----- | ----- |
|核心插件** | | | | **对应于默认核心阶段（即清理，编译）的插件。他们也可能有多个目标。
| [`干净][54] | B | 3.0.0 | 2015-10-22 |清理后建成。| [SVN][55] | [JIRA][56] |
| [`compiler`][57] | B | 3.7.0 | 2017-09-04 |编译Java源码。| [SVN][58] | [JIRA][59] |
| [`deploy`][60] | B | 2.8.2 | 2014-08-27 |将构建的工件部署到远程存储库。| [SVN][61] | [JIRA][62] |
| [`failsafe`][63] | B | 2.20.1 | 2017-09-15 |在隔离的类加载器中运行JUnit集成测试。| [GIT][64] | [JIRA][65] |
| [`install`][66] | B | 2.5.2 | 2014-08-27 |将构建的工件安装到本地存储库中。| [SVN][67] | [JIRA][68] |
| [`resources`][69] | B | 3.0.2 | 2016-12-10 |将资源复制到输出目录以包含在JAR中。 | [SVN][70] | [JIRA][71] |
| [`site`][72] | B | 3.6 | 2016-11-17 |为当前项目生成一个站点。| [SVN][73] | [JIRA][74] |
| [`surefire`][75] | B | 2.20.1 | 2017-09-15 |在隔离的类加载器中运行JUnit单元测试。| [GIT][64] | [JIRA][65] |
| [`verifier`][76] | B | 1.1 | 2015-04-14 |用于集成测试 - 验证某些条件的存在。| [SVN][77] | [JIRA][78] |
| **包装类型/工具** | | | | **这些插件涉及打包各种工件类型。
| [`ear`][79] | B | 2.10.1 | 2015-06-27 |从当前项目生成EAR。| [SVN][80] | [JIRA][81] |
| [`ejb`][82] | B | 3.0.0 | 2017-08-13 |从当前项目构建EJB（和可选客户端）。| [SVN][83] | [JIRA][84] |
| [`jar`][85] | B | 3.0.2 | 2016-06-18 |从当前项目构建JAR。| [SVN][86] | [JIRA][87] |
| [`rar`][88] | B | 2.4 | 2014-09-08 |从当前项目构建RAR。| [SVN][89] | [JIRA][90] |
| [`war`][91] | B | 3.1.0 | 2017-04-26 |从当前项目构建一个WAR。| [SVN][92] | [JIRA][93] |
| [`app-client / acr`][94] | B | 3.0.0 | 2015-01-23 |从当前项目构建JavaEE应用程序客户端。| [SVN][95] | [JIRA][96] |
| [`shade`][97] | B | 3.1.0 | 2017-08-22 |从当前项目构建Uber-JAR，包括依赖关系。| [SVN][98] | [JIRA][99] |
| [`source`][100] | B | 3.0.1 | 2016-06-18 |从当前项目构建源JAR。| [SVN][101] | [JIRA][102] |
| **报告插件** | | | | **生成报告的插件被配置为POM中的报告，并在站点生成周期内运行。
| [`changelog`][103] | R | 2.3 | 2014-06-24 |从您的SCM生成最近更改的列表。 | [SVN][104] | [JIRA][105] |
| [`changes`][106] | B + R | 2.12.1 | 2016-11-01 |从问题跟踪器或更改文档生成报告。| [SVN][107] | [JIRA][108] |
| [`checkstyle`][109] | B + R | 2.17 | 2015-10-15 |生成Checkstyle报告。| [SVN][110] | [JIRA][111] |
| [`doap`][112] | B | 1.2 | 2015-03-17 |从POM生成项目描述（DOAP）文件。 | [SVN][113] | [JIRA][114] |
| [`docck][115] | B | 1.1 | 2015-04-03 |文档检查插件。| [SVN][116] | [JIRA][117] |
| [`javadoc`][118] | B + R | 3.0.0-M1 | 2017-07-21 |为项目生成Javadoc。| [SVN][119] | [JIRA][120] |
| [`jdeps`][121] | B | 3.1.0 | 2017-09-02 |在项目中运行JDK的JDeps工具。| [SVN][122] | [JIRA][123] |
| [`jxr`][124] | R | 2.5 | 2014-11-02 |生成源交叉引用。| [SVN][125] | [JIRA][126] |
| [`linkcheck`][127] | R | 1.2 | 2014-10-08 |生成项目文档的Linkcheck报告。| [SVN][128] | [JIRA][129] |
| [`pmd`][130] | B + R | 3.8 | 2017-05-05 |生成PMD报告。| [SVN][131] | [JIRA][132] |
| [`project-info-reports`][133] | R | 2.9 | 2016-03-01 |生成标准项目报告。| [SVN][134] | [JIRA][135] |
| [`surefire-report`][136] | R | 2.20.1 | 2017-09-15 |根据单元测试的结果生成报告。| [GIT][64] | [JIRA][65] |
| **工具** | | | | **这些是默认情况下通过Maven可用的各种工具。
| [`ant`][137] | B | 2.4 | 2014-12-15 |为项目生成Ant构建文件。| [SVN][138] | [JIRA][139] |
| [`antrun`][140] | B | 1.8 | 2014-12-26 |从构建阶段运行一组蚂蚁任务。| [SVN][141] | [JIRA][142] |
| [`archetype`][143] | B | 3.0.1 | 2017-04-11 |从原型生成骨架项目结构。| [GIT][144] | [JIRA][145] |
| [`assembly`][146] | B | 3.1.0 | 2017-08-13 |构建源和/或二进制文件的汇编（分发）。| [SVN][147] | [JIRA][148] |
| [`dependency`][149] | B + R | 3.0.1 | 2017-05-11 |依赖操纵（复制，解包）和分析。| [SVN][150] | [JIRA][151] |
| [`执行者][152] | B | 3.0.0-M1 | 2017-07-30 |环境约束检查（Maven版本，JDK等），用户自定义规则执行。| [SVN][153] | [JIRA][154] |
| [`gpg`][155] | B | 1.6 | 2015-01-19 |为工件和pom创建签名。| [SVN][156] | [JIRA][157] |
| [`help`][158] | B | 2.2 | 2013-02-23 |获取有关项目工作环境的信息。| [SVN][159] | [JIRA][160] |
| [`invoker`][161] | B + R | 3.0.1 | 2017-07-21 |运行一组Maven项目并验证输出。| [SVN][162] | [JIRA][163] |
| [`jarsigner`][164] | B | 1.4 | 2015-01-21 |标识或验证项目工件。| [SVN][165] | [JIRA][166] |
| [`patch`][167] | B | 1.2 | 2015-03-09 |使用gnu补丁工具将补丁文件应用到源代码。| [SVN][168] | [JIRA][169] |
| [`pdf`][170] | B | 1.3 | 2015-02-16 |生成项目文档的PDF版本。| [SVN][171] | [JIRA][172] |
| [`plugin`][173] | B + R | 3.5 | 2016-08-30 |为源树中找到的任何moj创建Maven插件描述符，以包含在JAR中。 | [SVN][174] | [JIRA][175] |
| [`release`][176] | B | 2.5.3 | 2015-10-17 |释放当前项目 - 在SCM中更新POM和标记。 | [SVN][177] | [JIRA][178] |
| [`remote-resources`][179] | B | 1.5 | 2013-08-14 |将远程资源复制到输出目录以包含在工件中。| [SVN][180] | [JIRA][181] |
| [`repository`][182] | B | 2.4 | 2015-02-22 |帮助基于存储库的任务的插件。| [SVN][183]​​ | [JIRA][184] |
| [`scm`][185] | B | 1.9.5 | 2016-07-01 |对当前项目执行SCM命令。| [GIT][186] | [JIRA][187] |
| [`scm-publish`][188] | B | 1.1 | 2014-05-18 |将您的Maven网站发布到scm位置。| [SVN][189] | [JIRA][190] |
| [`stage`][191] | B | 1.0 | 2015-03-03 |协助发布分期和推广。| [SVN][192] | [JIRA][193] |
| [`toolchains`][194] | B | 1.1 | 2014-11-12 |允许跨插件共享配置。| [SVN][195] | [JIRA][196] |

* ** B ** uild或** R ** eporting插件

我们的[源库]还有一些沙盒插件[197]。

以前存档的插件版本参考文献[位于][198]。

### 退休


| **插件** | **类型*** | **版本** | **退休日期** | **说明** |
| ----- |----- |----- |----- |
| [`eclipse`][199] | B | 2.10 | 2015-10-07 |为当前项目生成Eclipse项目文件。
| [`idea`][200] | B | 2.2.1 | 2013-07-26 |创建/更新当前项目的IDEA工作区（各个模块创建为IDEA模块）|
| [`one`][201] | B | 1.3 | 2013-07-30 |用于与传统Maven 1.x存储库和构建体进行交互的插件。
| [`reactor`][202] | B | 1.1 | 2014-03-24 |在反应堆中构建一个相互依赖项目的子集（仅限Maven 2）。|

### Outside The Maven Land

#### 在codehaus.org

“由于关闭了codehaus.org [所有插件都在转换][203]到新的位置。这意味着目前的一些链接可能无效。我们一直在清理链接。`

在GitHub的[MojoHaus][205]项目中还有[许多插件][204]。

这里有几个常见的：

| **插件**（参见[完整列表版本][204]）| **说明** |
| ----- |----- |
| [`动物嗅探器][206] |构建API的签名（例如JDK），并根据它们检查类。
| [`build-helper`][207] |附加额外的工件和源文件夹进行构建。
| [`castor`][208] |使用Castor从XSD生成源。
| [`clirr`][209] |使用Clirr比较二进制或兼容性来源
| [`javacc`][210] |从JavaCC语法生成源。1927
| [`jdepend`][211] |使用JDepend生成关于代码度量的报告。
| [`nar-maven-plugin`][212] |针对不同架构编译C，C ++，Fortran。
| [`native`][213] |用本地编译器编译C和C ++代码。
| [`sql`][214] |从文件或内联执行SQL脚本。
| [`taglist`][215] |根据代码中的标签生成任务列表。
| [`版本][216] |管理项目的版本，其模块，依赖关系和插件。|

####在code.google.com

[Google Code][218]还有[许多插件][217]。

#### MISC

许多其他项目提供自己的Maven插件。具体包括：

| **插件** | **维护者** | **说明** |
|----- |----- |----- |
| [`cargo`][219] | [Cargo Project][219] |启动/停止/配置J2EE容器并部署到它们。
| [`clover`][220] | [Atlassian Clover][221] |生成三叶草报告。
| [`jetty`][222] | [Jetty Project][223] | Jetty运行Jetty容器，用于快速webapp开发。1927
| [`jalopy`][224] | [Triemax][225] |使用Jalopy格式化您的源代码。
| [`rat`][226] | [Apache Creadur Project][227] |发布审核工具（RAT）来验证文件。
| [`Genesis Plugins`][228] | [Apache Geronimo Project][229] |验证工件中的合法文件。
| [`Apache Tomcat`][230] | [Apache Tomcat Project][230] |运行Apache Tomcat容器以快速开发webapp。|

### 资源

1.[配置插件指南][231]



Apache软件基金会 版权所有 2013版权所有。

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

</报告> </建造>
