

[来源]（https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html“固定链接到Maven - Maven 5分钟”）

＃Maven - Maven 5分钟

5分钟内的

• {0}先决条件{/0} ：

您必须了解如何在计算机上安装软件。如果你不知道该怎么做，请问你的办公室，学校等人，或者向某人解释这个问题。Maven邮件列表不是最好的地方要求这个建议。

• {0}安装{/0} ：

_Maven是一个Java工具，所以你必须安装[Java] [57]才能继续。_

首先，[下载Maven] [58]并按照[安装说明] [59]。之后，在终端或命令提示符下键入以下内容：


mvn --version

它应该打印出你安装的Maven版本，例如：


Apache Maven 3.0.5（r01de14724cdef164cd33c7c8c2fe155faf9602da; 2013-02-19 14：51：28 + 0100）
Maven主页：D：apache-maven-3.0.5bin ..
Java版本：1.6.0_25，供应商：Sun Microsystems Inc.
Java主页：C：Program FilesJavajdk1.6.0_25jre
默认语言环境：nl_NL，平台编码：Cp1252
操作系统名称：“windows 7”，版本：“6.1”，arch：“amd64”，系列：“windows”

根据您的网络设置，您可能需要额外的配置。如果需要，请查看[配置Maven指南] [60]。

**如果您正在使用Windows，则应该查看** [Windows先决条件] [61] **，以确保您准备在Windows上使用Maven。**

创建一个项目

您将需要某个地方驻留您的项目，在某个地方创建一个目录，并在该目录中启动一个shell。在您的命令行中，执行以下Maven目标：


mvn archetype：generate -DgroupId = com.mycompany.app -DartifactId = my-app -DarchetypeArtifactId = maven-archetype-quickstart -DinteractiveMode = false

_如果你刚刚安装Maven，可能需要一段时间在第一次运行。这是因为Maven将最新的工件（插件罐和其他文件）下载到本地存储库中。您可能还需要在成功之前执行该命令几次。这是因为在您的下载完成之前，远程服务器可能会超时。别担心，有办法解决这个问题。_

您将注意到_generate_目标创建了一个与artifactId相同名称的目录。切换到该目录。


cd我的应用程序

在这个目录下，您将注意到以下[标准项目结构] [62]。


我的应用程序内
| - pom.xml
{0}{1}src{/1}{/0} :
主要
```java
com
| ` - 我的公司
AP2P
| ` - App.java
测试
```java
com
` - 我的公司
AP2P
` - AppTest.java

`src / main / java`目录包含项目源代码，`src / test / java`目录包含测试源，`pom.xml`文件是项目的项目对象模型（POM）。

#### POM

“pom.xml”文件是Maven中项目配置的核心。它是一个单一的配置文件，其中包含了以所需方式构建项目所需的大部分信息。POM是巨大的，可能在复杂性方面令人生畏，但是没有必要了解所有的复杂性，还没有有效地使用它。这个项目的POM是：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd“>
<modelversion> 4.0.0 </ modelversion>

<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的> MY-应用</ artifactId的>
<版本> 1.0-SNAPSHOT </版本>
<包装>罐</包装>

<name> Maven Quick Start Archetype </ name>
<URL> http://maven.apache.org </ URL>

<依赖性>
<dependency>
<GROUPID>的junit </ GROUPID>
<artifactId的>的junit </ artifactId的>
  <version>2.12</version>
<范围>测试</范围>
<dependency>
</依赖>
<project>

####我刚做什么？

您执行了Maven目标_archetype：generate_，并将其传递给该目标的各种参数。前缀_archetype_是包含目标的[plugin] [63]。如果您熟悉[Ant] [64]，则可以将其设计为类似于任务。这个目标创建了一个基于原型的简单项目。现在说现在，一个_plugin_是_goals_的集合，具有一般的共同目的。例如，jboss-maven-plugin，其目的是“处理各种jboss项目”。

####构建项目


mvn包

命令行将打印出各种操作，并结束如下：



信息
[INFO] BUILD SUCCESSFUL
信息
[INFO]总时间：2秒
[INFO]完成于：Thu Jul 07 21:34:52 CEST 2011
[INFO] Final Memory：3M / 6M
信息

与执行的第一个命令（_archetype：generate_）不同，您可能会注意到第二个命令只是一个单一的字 - _package_。而不是一个目标，这是一个_phase_。阶段是[构建生命周期] [65]中的一个阶段，这是阶段的有序序列。当给出相位时，Maven将执行序列中的每个阶段，直到并包括定义的阶段。例如，如果我们执行_compile_阶段，实际执行的阶段是：

验证
2.生成源
过程来源
4.生成资源
5.流程资源
编译

您可以使用以下命令测试新编译和打包的JAR：


java -cp target / my-app-1.0-SNAPSHOT.jar com.mycompany.app。AP2P

哪个将打印典型的：


11. 你好，世界！

###运行Maven工具

#### Maven阶段

尽管几乎不是一个全面的列表，但它们是执行的最常见的_default_生命周期阶段。

* **验证**：验证项目是正确的，所有必要的信息可用
* **编译**：编译项目的源代码
* ** test **：使用合适的单元测试框架测试编译的源代码。这些测试不应该要求代码被打包或部署
* **包**：采用编译后的代码，并以其可分配格式（如JAR）进行打包。
* **集成测试**：如果需要，可以将包过程并部署到可以运行集成测试的环境中
* **验证**：运行任何检查以验证包是否有效并符合质量标准
* **安装**：将软件包安装到本地存储库中，用作本地其他项目的依赖项
* **部署**：在集成或发布环境中完成，将最终软件包复制到远程存储库，以与其他开发人员和项目共享。

除了上面的_default_列表之外，还有另外两个Maven生命周期。他们

* ** clean **：清理先前版本创建的工件
* **网站**：生成此项目的站点文档

阶段实际上映射到基本目标。每个阶段执行的具体目标取决于项目的包装类型。例如，如果项目类型是JAR，_package_将执行_jar：jar_，而_war：war_如果项目类型是您猜测的 - 一个WAR。

需要注意的一个有趣的事情是，阶段和目标可以按顺序执行。


mvn clean依赖：copy-dependencies包

此命令将清理项目，复制依赖项，并打包项目（当然执行所有阶段最多为_package_）。

####生成网站


mvn网站

该阶段根据项目的pom的信息生成一个站点。您可以查看“target / site”下生成的文档。

结论

我们希望这个快速的概述引发了您对Maven多功能性的兴趣。请注意，这是一个非常截短的快速入门指南。现在，您已准备好了解您刚刚执行的操作的更全面的详细信息。查看[Maven入门指南] [66]。



Apache软件基金会 版权所有 2013版权所有。

[1]：https：//maven.apache.org/images/apache-maven-project.png
[2]：https：//maven.apache.org/images/maven-logo-black-on-white.png
[3]：https://www.apache.org/“Apache”
[4]：https://maven.apache.org/index.html“Maven”
[5]：https://maven.apache.org/index.html“欢迎”
[6]：https://www.apache.org/licenses/“许可证”
[7]：https://maven.apache.org/download.html“下载”
[8]：https://maven.apache.org/install.html“安装”
[9]：https://maven.apache.org/configure.html“配置”
[10]：https://maven.apache.org/run.html“运行”
[11]：https://maven.apache.org/ide.html“IDE集成”
[12]：https://maven.apache.org/what-is-maven.html“什么是Maven？”
[13]：https://maven.apache.org/maven-features.html“功能”
[14]：https://maven.apache.org/general.html“常见问题”
[15]：https://maven.apache.org/support-and-training.html“支持与培训”
[16]：https://maven.apache.org/plugins/index.html“Maven插件”
[17]：https://maven.apache.org/guides/index.html“索引（类别）”
[18]：https://maven.apache.org/run-maven/index.html“运行Maven”
[19]：https://maven.apache.org/users/index.html“用户中心”
[20]：https：//maven.apache.org#
[21]：https://maven.apache.org/guides/getting-started/index.html“入门指南”
[22]：https://maven.apache.org/users/getting-help.html“获取帮助”
[23]：https://maven.apache.org/settings.html“设置参考”
[24]：https://maven.apache.org/pom.html“POM参考”
[25]：https://maven.apache.org/plugin-developers/index.html“插件开发人员中心”
[26]：https://maven.apache.org/repository/index.html“Maven Central Repository”
[27]：https://maven.apache.org/developers/index.html“Maven开发人员中心”
[28]：https://maven.apache.org/articles.html“图书与资源”
[29]：https://maven.apache.org/security.html“安全”
[30]：https://maven.apache.org/community.html“社区概述”
[31]：https://maven.apache.org/guides/development/guide-helping.html“如何贡献”
[32]：https://maven.apache.org/guides/mini/guide-maven-evangelism.html“Maven Repository”
[33]：https://maven.apache.org/issue-tracking.html“问题跟踪”
[34]：https://maven.apache.org/source-repository.html“源存储库”
[35]：https：//maven.apache.org/team-list.html“The Maven Team”
[36]：https://maven.apache.org/project-info.html“项目信息”
[37]：https://maven.apache.org/archetype/index.html“原型”
[38]：https://maven.apache.org/resolver/index.html“神器解析器”
[39]：https://maven.apache.org/doxia/index.html“Doxia”
[40]：https://maven.apache.org/jxr/index.html“JXR”
[41]：https://maven.apache.org/ref/current“Maven”
[42]：https：//maven.apache.org/pom/index.html“父POM”
[43]：https://maven.apache.org/plugins/index.html“插件”
[44]：https://maven.apache.org/plugin-testing/index.html“插件测试”
[45]：https://maven.apache.org/plugin-tools/index.html“插件工具”
[46]：https://maven.apache.org/apache-resource-bundles/index.html“资源包”
[47]：https://maven.apache.org/scm/index.html“SCM”
[48]：https://maven.apache.org/shared/index.html“共享组件”
[49]：https://maven.apache.org/skins/index.html“皮肤”
[50]：https://maven.apache.org/surefire/index.html“Surefire”
[51]：https：//maven.apache.org/wagon/index.html“Wagon”
[52]：https://www.apache.org/foundation/how-it-works.html“Apache如何工作”
[53]：https://www.apache.org/foundation/“基金会”
[54]：https://www.apache.org/foundation/sponsorship.html“赞助Apache”
[55]：https://www.apache.org/foundation/thanks.html“谢谢”
[56]：https：//maven.apache.org/images/logos/maven-feather.png
[57]：http://www.oracle.com/technetwork/java/javase/downloads/index.html
[58]：https：//maven.apache.org/download.html
[59]：https://maven.apache.org/download.html#Installation
[60]：https://maven.apache.org/mini/guide-configuring-maven.html
[61]：https://maven.apache.org/windows-prerequisites.html
[62]：https：//maven.apache.org/introduction/introduction-to-the-standard-directory-layout.html
[63]：https：//maven.apache.org/plugins/index.html
[64]：http://ant.apache.org
[65]：https：//maven.apache.org/introduction/introduction-to-the-lifecycle.html
[66]：https：//maven.apache.org/index.html
[67]：https：//www.apache.org/
