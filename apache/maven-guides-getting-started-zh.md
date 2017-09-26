
[来源]（https://maven.apache.org/guides/getting-started/index.html“永久链接到Maven - Maven入门指南”）

# Maven - Maven入门指南

## Maven入门指南

本指南旨在作为第一次与Maven合作的人员的参考，但也旨在作为具有独立参考和适用于常见用例的解决方案的食谱。对于第一次使用者，建议您按顺序浏览材料。对于更熟悉Maven的用户，本指南将为您提供快速解决方案。在这一点上假设您已经下载了Maven并在本地机器上安装了Maven。如果没有这样做，请参阅[下载和安装][57]说明。

好的，所以你现在安装了Maven，我们准备好了。在我们进入我们的例子之前，我们将简要介绍一下Maven是什么，以及如何帮助您与团队成员进行日常工作和协作。当然，Maven将为小型项目工作，但是Maven通过允许团队成员专注于项目的利益相关者需要，帮助团队更有效地运作。您可以将构建基础架构保留到Maven！

## 分段

* [什么是Maven？][58]
* [Maven如何有益于我的发展过程？][59]
* [如何设置Maven？][60]
* [如何使我的第一个Maven项目？][61]
* [如何编译我的应用程序源？][62]
* [如何编译测试源并运行我的单元测试？][63]
* [如何创建JAR并将其安装在本地存储库中？][64]
* [什么是SNAPSHOT版本？][65]
* [如何使用插件？][66]
* [如何添加资源到我的JAR？][67]
* [如何过滤资源文件？][68]
* [如何使用外部依赖关系？][69]
* [如何在我的远程存储库中部署我的jar？][70]
* [如何创建文档？][71]
* [如何建立其他类型的项目？][72]
* [如何一次构建多个项目？][73]

### 什么是Maven？

乍看之下，Maven似乎有许多事情，但简而言之，Maven是一种尝试 - 将模式应用于项目的构建基础设施，以通过提供使用最佳实践的明确途径来提高理解和生产力。Maven本质上是一个项目管理和理解工具，因此提供了一种帮助管理的方法：

攻略
* 文档
报告
显式上下文相关性。
*单片机
*发布
在体内的分布

如果你想要更多的Maven背景信息，你可以查看[Maven的哲学][74]和[Maven的历史][75]。现在我们来看看用户如何从使用Maven中获益。

### Maven如何有益于我的开发过程？

Maven可以通过采用标准的惯例和实践为您的构建过程提供好处，从而加快开发周期，同时帮助您实现更高的成功率。

现在，我们已经涵盖了Maven的一些历史和目的，让我们进一步了解一些真正的例子，让你和Maven一起运行！

###如何设置Maven？

Maven的默认值通常是足够的，但是如果您需要更改缓存位置或者在HTTP代理之后，您将需要创建配置。有关详细信息，请参阅[配置Maven指南][76]。

###如何使我的第一个Maven项目？

我们要跳过创建你的第一个Maven项目！要创建我们的第一个Maven项目，我们将使用Maven的原型机制。原型被定义为_原始图案或模型，其中所有其他同类物品都被制成_。在Maven中，原型是一个项目的模板，与一些用户输入相结合，以生成针对用户要求定制的工作Maven项目。我们将向您展示原型机构的工作原理，但如果您想了解更多关于原型的信息，请参阅我们的[原型简介][77]。

在创建你的第一个项目！为了创建最简单的Maven项目，请从命令行执行以下操作：


mvn -B原型：生成
-DarchetypeGroupId = org.apache.maven.archetypes
-DgroupId = com.mycompany.app
-DartifactId =我的应用程序内

一旦你执行了这个命令，你会注意到一些事情发生了。首先，您将注意到，为新项目创建了一个名为`my-app`的目录，此目录包含一个名为`pom.xml`的文件，应该如下所示：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
<modelversion> 4.0.0 </ modelversion>
<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的> MY-应用</ artifactId的>
<包装>罐</包装>
<版本> 1.0-SNAPSHOT </版本>
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

`pom.xml'包含此项目的项目对象模型（POM）。POM是Maven的基本工作单位。这很重要，因为Maven本质上是以项目为中心的，因为一切都围绕一个项目的概念。简而言之，POM包含有关您的项目的所有重要信息，并且基本上是一站式购物，以查找与您的项目相关的任何内容。了解POM是重要的，鼓励新用户参考[POM简介][78]。

这是一个非常简单的POM，但仍然显示每个POM包含的关键元素，所以让我们走过每一个，以熟悉POM要点：

* ** project **这是所有Maven pom.xml文件中的顶级元素。
* ** modelVersion **此元素指示该POM正在使用的对象模型的版本。模型本身的版本很少变化，但是如果Maven开发人员认为有必要更改模型，那么为了确保使用的稳定性是必须的。
* ** groupId **此元素表示创建项目的组织或组的唯一标识符。groupId是项目的关键标识符之一，通常基于您组织的完全限定域名。例如`org.apache.maven.plugins`是所有Maven插件的指定的groupId。
* ** artifactId **此元素表示此项目正在生成的主要工件的唯一基本名称。项目的主要工件通常是JAR文件。诸如源码包之类的辅助工件也会使用artifactId作为其最终名称的一部分。Maven生成的一个典型的工件将有<artifactid> - <version>。<extension>（例如`myapp-1.0.jar`）。
* **包装**此元素指示此工件使用的包类型（例如JAR，WAR，EAR等）。这不仅意味着如果生成的工件是JAR，WAR或EAR，但也可以指示在构建过程中使用的特定生命周期。（生命周期是我们将在指南中进一步处理的一个主题。现在，请记住，指定的项目包装可以在定制构建生命周期中发挥作用。）`packaging`元素的默认值是JAR，所以你不必为大多数项目指定。
* ** version **此元素指示项目生成的工件的版本。Maven可以帮助您进行版本管理，您将会在“版本”中看到“SNAPSHOT”指示符，这表明项目处于开发状态。我们将在本指南中讨论[快照][65]的使用及其进一步工作。
* ** name **此元素指示用于项目的显示名称。这通常用在Maven生成的文档中。
* ** url **此元素表示可以找到项目的网站。这通常用在Maven生成的文档中。
* **描述**此元素提供了您的项目的基本描述。这通常用在Maven生成的文档中。

有关可用于POM的元素的完整参考，请参阅我们的[POM参考][79]。现在让我们回到手头的项目。

在您的第一个项目的原型生成之后，您还将注意到已创建以下目录结构：


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

如您所见，从原型创建的项目具有POM，应用程序源的源代码树和测试源的源代码树。这是Maven项目的标准布局（应用程序源位于`$ {basedir} / src / main / java`）中，测试源位于`$ {basedir} / src / test / java`中，其中$ {basedir}表示包含`pom.xml'的目录）。

如果要手动创建一个Maven项目，这是我们建议使用的目录结构。这是一个Maven大会，要了解更多信息，您可以阅读我们的[标准目录布局简介][80]。

现在我们有一个POM，一些应用程序源和一些测试源，你可能会问...

###如何编译我的应用程序源？

转到由archetype创建pom.xml的目录：generate并执行以下命令来编译应用程序源：


mvn编译

执行该命令后，您将看到如下所示的输出：


信息
[INFO]建筑Maven快速启动原型
[INFO]任务段：[编译]
信息
[INFO] artifact org.apache.maven.plugins：maven-resources-plugin：
检查中央的更新
1927
[INFO] artifact org.apache.maven.plugins：maven-compiler-plugin：
检查中央的更新

[资料][资源：资源]

[INFO][编译器：编译]
将1个源文件编译为<dir> / my-app / target / classes
信息
[INFO] BUILD SUCCESSFUL
信息
[INFO]总时间：3分54秒
[INFO]完成于：Fri Sep 23 15:48:34 GMT-05：00 2005
[INFO]最终内存：2M / 6M
信息

第一次执行（或任何其他）命令时，Maven将需要下载其完成命令所需的所有插件和相关依赖项。从一个干净安装的Maven，这可能需要相当长的一段时间（在上面的输出，花了差不多4分钟）。如果再次执行该命令，Maven现在将拥有所需的内容，因此不需要下载任何新内容，并能够更快地执行命令。

从输出可以看出，编译的类被放置在$ {basedir} / target / classes中，这是Maven使用的另一个标准约定。所以，如果你是一个敏锐的观察者，你会注意到，通过使用标准约定，上面的POM非常小，你不必明确地告诉Maven你的任何来源是什么，或输出应该在哪里。遵循标准的Maven约定，您可以用很少的精力完成很多工作！就像一个偶然的比较，让我们来看看你可能在[Ant][81]中做了什么来完成同样的事情[82]。

现在，这只是编译单个应用程序源树，并且显示的Ant脚本与上面显示的POM大致相同。但是，我们还可以看到我们可以用简单的POM做多少事情！

###如何编译测试源并运行我的单元测试？

现在，您正在成功编译应用程序的源码，现在您已经有一些要编译和执行的单元测试（因为每个程序员总是写入并执行单元测试*微调微调wink wink *）。

执行以下命令：


mvn测试

执行该命令后，您将看到如下所示的输出：


信息
[INFO]建筑Maven快速启动原型
[INFO] task-segment：[test]
信息
[INFO] artifact org.apache.maven.plugins：maven-surefire-plugin：
检查中央的更新

[资料][资源：资源]
[INFO][编译器：编译]
[INFO]无需编译 - 所有课程都是最新的
[INFO][resources：testResources]
[INFO][编译器：testCompile]
将1个源文件编译为C：TestMaven2testmy-apptargettest-classes

[INFO][surefire：test]
[INFO]设置报告目录：C：TestMaven2testmy-apptarget / surefire-reports

1927
要求检测

运行com.mycompany.app。AppTest
[surefire]测试运行：1，故障：0，错误：0，时间已过：0秒

结果：
[surefire]测试运行：1，失败：0，错误：0

信息
[INFO] BUILD SUCCESSFUL
信息
[INFO]总时间：15秒
[INFO]完成于：Thu Oct 06 08:12:17 MDT 2005
[INFO]最终内存：2M / 8M
信息

有些事情要注意的输出：

* Maven此次下载更多的依赖项。这些是执行测试所必需的依赖和插件（它已经具有编译所需的依赖关系，不会再次下载）。
*在编译和执行测试之前，Maven编译主代码（所有这些类都是最新的，因为我们编译最后没有改变任何东西）。

如果您只想编译测试源（但不执行测试），则可以执行以下操作：


mvn测试编译

现在您可以编译应用程序源，编译测试并执行测试，您将需要继续进行下一个逻辑步骤，以便您能够...

###如何创建JAR并将其安装在本地存储库中？

使JAR文件足够简单，可以通过执行以下命令来完成：


mvn包

如果您查看项目的POM，您将注意到`包装'元素设置为`jar`。这是Maven从上述命令中知道生成JAR文件的方式（稍后我们将再说一下）。现在可以看看`$ {basedir} / target`目录，你会看到生成的JAR文件。

现在，您需要将您生成的工件（JAR文件）安装到本地存储库中（`$ {user.home} /。m2 / repository`是默认位置）。有关存储库的更多信息，可参考我们的[存储库简介][83]，但我们继续安装我们的工件！为此执行以下命令：


mvn安装

执行此命令后，您将看到以下输出：


信息
[INFO]建筑Maven快速启动原型
[INFO]任务段：[安装]
信息
[资料][资源：资源]
[INFO][编译器：编译]
将1个源文件编译为<dir> / my-app / target / classes
[INFO][resources：testResources]
[INFO][编译器：testCompile]
将1个源文件编译到<dir> / my-app / target / test-classes
[INFO][surefire：test]
[INFO]设置报告目录：<dir> / my-app / target / surefire-reports

1927
要求检测

运行com.mycompany.app。AppTest
[surefire]测试运行：1，故障：0，错误：0，经过时间：0.001秒

结果：
[surefire]测试运行：1，失败：0，错误：0

[INFO][jar：jar]
[INFO]构建jar：<dir> /my-app/target/my-app-1.0-SNAPSHOT.jar
[INFO][安装：安装]
[INFO]将<dir> /my-app/target/my-app-1.0-SNAPSHOT.jar安装到
<本地储存库> /com/mycompany/app/my-app/1.0-SNAPSHOT/my-app-1.0-SNAPSHOT.jar
信息
[INFO] BUILD SUCCESSFUL
信息
[INFO]总时间：5秒
[INFO]完成于：Tue Oct 04 13:20:32 GMT-05：00 2005
[INFO] Final Memory：3M / 8M
信息

请注意，surefire插件（执行测试）会查找包含在具有特定命名约定的文件中的测试。默认情况下，测试包括：

*`** / * Test.java`
*`** / Test * .java`
*`** / * TestCase.java`

默认排除的是：

*`** / Abstract * Test.java`
*`** / Abstract * TestCase.java`

您已经完成了建立，构建，测试，打包和安装典型Maven项目的过程。这可能是绝大多数项目将与Maven一起工作，如果您注意到，您所能做的一切都是由18行文件驱动，即项目模型或POM。如果你看一个典型的Ant [build file][82]，提供了我们迄今为止所实现的相同的功能，你会注意到它已经是POM大小的两倍，我们刚刚开始！从Maven可以获得更多的功能，而不需要像现在这样添加POM。要从我们的示例Ant构建文件中获得更多的功能，您必须继续发生容易出错的添加。

那么还有什么可以免费获得的？有大量的Maven插件，即使是像上面那样简单的POM，也可以开箱即用。我们将特别提及这一个，因为它是Maven高度珍贵的功能之一：您没有任何工作，这个POM有足够的信息为您的项目生成一个网站！您最有可能要自定义您的Maven网站，但如果您按时完成所有您需要做的，以提供有关您的项目的基本信息，请执行以下命令：


mvn网站

还有很多其他可以执行的独立目标，例如：


mvn干净

这将在启动之前删除所有构建数据的“target”目录，以便它是新鲜的。

也许你想为项目生成一个IntelliJ IDEA描述符？


mvn想法：想法

这可以运行在以前的IDEA项目的顶部 - 它将更新设置，而不是开始新鲜。

如果您使用的是Eclipse IDE，只需调用：


mvn eclipse：eclipse

**注意：** Maven 1.0中的一些熟悉的目标仍然存在，例如“jar：jar”，但是它们的行为可能不如你所期望的那样。目前，`jar：jar`不会重新编译源代码 - 它只是简单地从`target / classes`目录创建一个JAR，假设已经完成了一切。

###什么是SNAPSHOT版本？

请注意，下面显示的`pom.xml`文件中的**版本**标签的值具有后缀：-SNAPSHOT。


<project xmlns =“http://maven.apache.org/POM/4.0.0”... =“”<groupid =“”> ...
<artifactId的> MY-应用</ artifactId的>
1927
<版本> 1.0-SNAPSHOT </版本>
<name> Maven Quick Start Archetype </ name>


“SNAPSHOT”值是指开发分支中的“最新”代码，不保证代码稳定或不变。相反，“release”版本中的代码（没有后缀“SNAPSHOT”的任何版本值）都是不变的。

换句话说，SNAPSHOT版本是最终“发布”版本之前的“开发”版本。SNAPSHOT比它的版本“老”。

在[release][84]过程中，** xy-SNAPSHOT **的版本更改为** xy **。发布过程还将开发版本增加到** x。（y + 1）-SNAPSHOT **。例如，版本** 1.0-SNAPSHOT **作为版本** 1.0 **发布，新的开发版本是版本** 1.1-SNAPSHOT **。

###如何使用插件？

无论何时要自定义Maven项目的构建，都可以通过添加或重新配置插件来实现。

**注意Maven 1.0用户：**在Maven 1.0中，您将添加一些“preGoal”到“maven.xml”，并将一些条目添加到“project.properties”。这里有点不同。

对于这个例子，我们将配置Java编译器以允许JDK 5.0源。这就像添加到您的POM一样简单：



</build>
    </plugins>
</plugin>
<groupId>org.apache.maven.plugins</groupId>
        <artifactId>maven-compiler-plugin</artifactId>
  <version>2.12</version>
  </configuration>
<source>
          <target>1.4</target>
  </configuration>
</plugin>
    </plugins>
</build>
1927

你会注意到，Maven中的所有插件看起来都像一个依赖关系 - 在某些方面它们是一样的。该插件将自动下载并使用 - 包括特定版本（如果您要求它）（默认是使用最新的）。

`configuration`元素将给定的参数应用于编译器插件的每个目标。在上述情况下，编译器插件已经被用作构建过程的一部分，这只是改变了配置。还可以为流程添加新目标，并配置特定目标。有关信息，请参阅[构建生命周期简介][85]。

要了解插件可用的配置，您可以看到[插件列表][86]，并导航到您正在使用的插件和目标。有关如何配置插件的可用参数的一般信息，请参阅[配置插件指南][87]。

###如何向我的JAR添加资源？

可以满足的另一个常见用例是，不需要更改我们上面提到的POM，就是在JAR文件中打包资源。对于这个常见任务，Maven再次依赖[标准目录布局][80]，这意味着通过使用标准的Maven约定，您可以通过将这些资源放在标准目录结构中来将资源封装在JAR中。

您在下面的示例中看到，我们添加了目录“$ {basedir} / src / main / resources”，我们将我们希望在JAR中打包的任何资源放入其中。 Maven使用的简单规则就是：将`$ {basedir} / src / main / resources`目录中的任何目录或文件打包在JAR中，从JAR的底部开始，完全相同的结构。


我的应用程序内
| - pom.xml
{0}{1}src{/1}{/0} :
主要
```java
com
| | ` - 我的公司
AP2P
| | ` - App.java
{0}资源{/0} {1}              {/1} {2}13{/2}
META-INF/
| ` - application.properties
测试
```java
com
` - 我的公司
AP2P
` - AppTest.java

所以你可以在我们的例子中看到我们有一个'META-INF'目录，在该目录下有一个`application.properties`文件。如果您解压缩Maven为您创建的JAR，并查看它，您将看到以下内容：


META-INF/
| | - MANIFEST.MF
| | - application.properties
Maven
| ` - com.mycompany.app
| ` - 我的应用程式
| | - pom.properties
| ` - pom.xml
com
` - 我的公司
AP2P
` - App.class

如您所见，可以从JAR的底部找到`$ {basedir} / src / main / resources`的内容，我们的`application.properties`文件放在META-INF目录下。您还会注意到一些其他文件，如“META-INF / MANIFEST.MF”以及“pom.xml”和“pom.properties”文件。这些标准是在Maven中生成JAR。如果您选择，您可以创建自己的清单，但如果没有，Maven将默认生成一个清单。（您也可以修改默认清单中的条目，稍后我们将会介绍。）“pom.xml”和“pom.properties”文件被打包在JAR中，以便Maven生成的每个工件都是自我描述的，并且还允许您在需要时利用自己的应用程序中的元数据。一个简单的用法可能是检索您的应用程序的版本。在POM文件上操作将需要您使用一些Maven实用程序，但可以使用标准Java API使用属性，如下所示：


＃由Maven生成
#Tue Oct 04 15:43:21 GMT-05：00 2005
版本= 1.0-SNAPSHOT
的groupId = com.mycompany.app
的artifactId =我的应用程序内

要将单元测试的类路径添加资源，您将按照与向JAR添加资源的方式相同的模式，除了放置资源的目录是$ {basedir} / src / test / resources。此时，您将有一个项目目录结构，如下所示：


我的应用程序内
| - pom.xml
{0}{1}src{/1}{/0} :
主要
```java
com
| | ` - 我的公司
AP2P
| | ` - App.java
{0}资源{/0} {1}              {/1} {2}13{/2}
META-INF/
| | - application.properties
测试
```java
com
| ` - 我的公司
AP2P
| ` - AppTest.java
{0}资源{/0} {1}              {/1} {2}13{/2}
` - test.properties

在单元测试中，您可以使用以下代码的简单代码片段来访问测试所需的资源：




//检索资源
InputStream is = getClass（）。getResourceAsStream（“/test.properties”）;

//用资​​源做某事



###如何过滤资源文件？

有时，资源文件将需要包含只能在构建时提供的值。要在Maven中完成此操作，请使用语法`$ {<property name =“”}“将包含该值的属性引用到资源文件中。该属性可以是您的pom.xml中定义的值之一，在用户的settings.xml中定义的值，外部属性文件中定义的属性或系统属性。

为了在复制时拥有Maven过滤器资源，只需将`filter'设置为`pom.xml'中的资源目录即可：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
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

</build>
</resources>
<资源>
<目录>的src /主/资源</目录>
<滤波>真</过滤>
</资源>
</resources>
</build>
<project>

您会注意到，我们必须添加以前不存在的“build”，“resources”和“resource”元素。此外，我们必须明确指出资源位于src / main / resources目录中。所有这些信息都是作为默认值提供的，但由于`filter`的默认值为false，所以我们必须将其添加到我们的pom.xml中，以覆盖该默认值并将`filtering`设置为true。

要引用在pom.xml中定义的属性，属性名称使用定义值的XML元素的名称，“pom”被允许作为项目（root）元素的别名。所以`$ {project.name}`指的是项目的名称，`$ {project.version}`指的是项目的版本，`$ {project.build.finalName}'指的是最终的名字在构建项目打包时创建的文件等。请注意，POM的某些元素具有默认值，因此不需要在“pom.xml”中显式定义可用的值。类似地，可以使用以“settings”开头的属性名称来引用用户的`settings.xml`中的值（例如``$ {settings.localRepository}'指的是用户的本地存储库的路径）。

为了继续我们的例子，我们在`application.properties`文件（我们放在`src / main / resources`目录中）添加一些属性，当这个资源被过滤时，它们的值将被提供：


＃application.properties
application.name = $ {} project.name
application.version = $ {} project.version

有了这一点，您可以执行以下命令（process-resources是构建生命周期阶段，资源被复制和过滤）：


mvn进程资源

和`target / classes`下的`application.properties`文件（最终会进入jar）看起来像这样：


＃application.properties
application.name = Maven快速启动原型
application.version = 1.0-SNAPSHOT

要引用外部文件中定义的属性，您需要做的是在pom.xml中添加对该外部文件的引用。首先，我们创建我们的外部属性文件，并将其称为“src / main / filters / filter.properties”：


＃filter.properties
my.filter.value =您好！

接下来，我们将在`pom.xml`中添加对这个新文件的引用：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
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

</build>
<滤波器>
<滤波器>的src /主/滤波器/ filter.properties </过滤器>
</过滤器>
</resources>
<资源>
<目录>的src /主/资源</目录>
<滤波>真</过滤>
</资源>
</resources>
</build>
<project>

然后，如果我们在`application.properties`文件中添加对此属性的引用：


＃application.properties
application.name = $ {} project.name
application.version = $ {} project.version
消息= $ {my.filter.value}

`mvn process-resources`命令的下一个执行将把我们的新属性值放入`application.properties`中。作为在外部文件中定义my.filter.value属性的替代方法，您还可以在“pom.xml”的“properties”部分中定义它，您将获得相同的效果（请注意，我不会需要引用`src / main / filters / filter.properties`）：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
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

</build>
</resources>
<资源>
<目录>的src /主/资源</目录>
<滤波>真</过滤>
</资源>
</resources>
</build>

<Properties>
<my.filter.value>你好</my.filter.value>
<Properties>
<project>

过滤资源也可以从系统属性获取值; Java内置的系统属性（如“java.version”或“user.home”）或使用标准Java -D参数在命令行中定义的属性。为了继续这个例子，我们来更改我们的`application.properties`文件，看起来像这样：


＃application.properties
java.version = $ {} java.version
command.line.prop = $ {} command.line.prop

现在，当您执行以下命令（注意命令行上的command.line.prop属性的定义）时，“application.properties”文件将包含系统属性中的值。


mvn进程资源“-Dcommand.line.prop = hello again”

###如何使用外部依赖关系？

您可能已经注意到我们一直在使用的POM中的“dependencies”元素作为示例。事实上，你一直在使用一个外部的依赖关系，但是我们将在这里详细介绍一下这个工作原理。有关更全面的介绍，请参阅我们的[依赖机制介绍][88]。

pom.xml的“dependencies”部分列出了我们的项目需要构建的所有外部依赖项（无论是在编译时，测试时间，运行时间或其他任何时间都需要依赖关系）。现在，我们的项目仅仅依赖于JUnit（为了清楚起见，我取出了所有的资源过滤功能）：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
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

对于每个外部依赖关系，您需要定义至少4项：groupId，artifactId，version和scope。groupId，artifactId和版本与构建该依赖关系的项目的“pom.xml”中给出的相同。范围元素指示您的项目如何使用该依赖项，并且可以是像“compile”，“test”和“runtime”这样的值。有关可以为依赖项指定的所有内容的更多信息，请参阅[项目描述符参考][79]。

有关依赖机制的更多信息，请参阅[依赖机制简介][88]。

通过有关依赖关系的信息，Maven将在构建项目时引用依赖关系。Maven在哪里引用依赖关系？Maven在您的本地存储库（`$ {user.home} /。m2 / repository`是默认位置）中查找所有依赖项。在上一节[89]中，我们将项目（my-app-1.0-SNAPSHOT.jar）中的工件安装到本地存储库中。一旦它被安装在那里，另一个项目可以通过将依赖关系信息添加到它的pom.xml来引用该jar作为依赖：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的> MY-另一应用</ artifactId的>

<依赖性>
1927
<dependency>
<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的> MY-应用</ artifactId的>
<版本> 1.0-SNAPSHOT </版本>
<范围>编译</范围>
<dependency>
</依赖>
<project>

在别的地方建立依赖关系呢？他们如何进入我的本地存储库？每当项目引用本地存储库中不可用的依赖项时，Maven将从远程存储库下载依赖关系到本地存储库。您可能注意到Maven下载了很多东西，当您构建了您的第一个项目（这些下载是用于构建项目的各种插件的依赖关系）。默认情况下，可以在<http：repo.maven.apache.org =“”maven2 =“”>上找到（并浏览）远程存储库Maven。您还可以设置自己的远程存储库（可能是您的公司的中央存储库），而不是默认的远程存储库或除了默认的远程存储库。有关存储库的更多信息，请参阅[存储库简介][83]。

我们为我们的项目添加另一个依赖。假设我们在代码中添加了一些日志记录，需要添加log4j作为依赖关系。首先，我们需要知道log4j的groupId，artifactId和version是什么。我们可以浏览ibiblio并寻找它，或者通过搜索“site：www.ibiblio.org maven2 log4j”来帮助Google。搜索显示一个名为/ maven2 / log4j / log4j（或/ pub / packages / maven2 / log4j / log4j）的目录。该目录是一个名为maven-metadata.xml的文件。以下是log4j的maven-metadata.xml的内容：


  </metadata>
<GROUPID> log4j的</ GROUPID>
<artifactId的> log4j的</ artifactId的>
  <version>2.12</version>
<版本>
<版本>
  <version>2.12</version>
  <version>2.12</version>
  <version>2.12</version>
  <version>2.12</version>
  <version>2.12</version>
  <version>2.12</version>
  <version>2.12</version>
  <version>2.12</version>
  <version>2.12</version>
</版本>
</版本管理>
  </metadata>

从这个文件中我们可以看到我们想要的groupId是“log4j”，而artifactId是“log4j”。我们看到很多不同的版本值可供选择;现在，我们将使用最新版本1.2.12（一些maven-metadata.xml文件也可以指定当前版本的版本）。除了maven-metadata.xml文件，我们可以看到与每个版本的log4j库相对应的目录。在这些内部，我们将找到实际的jar文件（例如log4j-1.2.12.jar）以及一个pom文件（这是依赖关系的pom.xml，表明它可能有其他依赖关系和其他信息）和另一个maven-metadata.xml文件。还有一个与这些文件对应的md5文件，其中包含这些文件的MD5哈希值。您可以使用它来验证库或找出您可能正在使用的特定库的哪个版本。

现在我们知道我们需要的信息，我们可以添加依赖关系到我们的pom.xml：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
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
<dependency>
<GROUPID> log4j的</ GROUPID>
<artifactId的> log4j的</ artifactId的>
  <version>2.12</version>
<范围>编译</范围>
<dependency>
</依赖>
<project>

现在，当我们编译项目（`mvn compile`）时，我们会看到Maven下载我们的log4j依赖关系。

###如何在我的远程存储库中部署我的jar？

要将jar部署到外部存储库，必须将pom.xml中的存储库url和connectiong的认证信息配置到settings.xml中的存储库。

以下是使用scp和username / password认证的示例：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
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
<dependency>
<GROUPID> org.apache.codehaus.plexus </ GROUPID>
<artifactId的>丛-utils的</ artifactId的>
  <version>2.12</version>
<dependency>
</依赖>

</build>
<滤波器>
<滤波器>的src /主/滤波器/ filters.properties </过滤器>
</过滤器>
</resources>
<资源>
<目录>的src /主/资源</目录>
<滤波>真</过滤>
</资源>
</resources>
</build>
<？





00:10:01,177 --> 00:10:02,594
<distributionmanagement>
<库>
<ID> myCompany的存储库</ ID>
<name> MyCompany Repository </ name>
<URL> SCP：//repository.mycompany.com/repository/maven2 </ URL>
</存储库>
</ distributionmanagement>
<project>


<settings xmlns =“http://maven.apache.org/SETTINGS/1.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/SETTINGS/1.0.0
http://maven.apache.org/xsd/settings-1.0.0.xsd“>

<服务器>
<服务器>
<ID> myCompany的存储库</ ID>
<用户名> jvanzyl </用户名>
<！ - 默认值为〜/ .ssh / id_dsa - >
<privatekey> / path / to / identity </ privatekey>（默认为〜/ .ssh / id_dsa）
<密码> my_key_passphrase </口令短语>
</服务器>
</服务器>

</设置>

请注意，如果要连接到sshd_confing中将“PasswordAuthentication”参数设置为“否”的openssh ssh服务器，则每次用户名/密码认证时都必须键入密码（尽管您可以使用其他ssh登录客户端输入用户名和密码）。在这种情况下，您可能需要切换到公钥认证。

在`settings.xml`中使用密码时应该小心。有关详细信息，请参阅[密码加密][90]。

###如何创建文档？

为了让您从Maven的文档系统开始，您可以使用原型机制来使用以下命令为现有项目生成一个站点：


mvn原型：生成
-DarchetypeGroupId = org.apache.maven.archetypes
-DarchetypeArtifactId =行家-原型现场
-DgroupId = com.mycompany.app
-DartifactId = MY-APP-网站

现在转到[创建网站的指南][91]，了解如何为项目创建文档。

###如何建立其他类型的项目？

请注意，生命周期适用于任何项目类型。例如，在基本目录中，我们可以创建一个简单的Web应用程序：


mvn原型：生成
-DarchetypeGroupId = org.apache.maven.archetypes
-DarchetypeArtifactId =行家-原型-web应用
-DgroupId = com.mycompany.app
-DartifactId = MY-web应用

请注意，这些都必须在一行上。这将创建一个名为`my-webapp`的目录，其中包含以下项目描述符：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
<modelversion> 4.0.0 </ modelversion>

<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的> MY-web应用</ artifactId的>
<版本> 1.0-SNAPSHOT </版本>
<包装>战</包装>

<依赖性>
<dependency>
<GROUPID>的junit </ GROUPID>
<artifactId的>的junit </ artifactId的>
  <version>2.12</version>
<范围>测试</范围>
<dependency>
</依赖>

</build>
<finalname> MY-web应用</ finalname>
</build>
<project>

请注意`<packaging>`元素 - 这将告诉Maven作为WAR构建。更改到webapp项目的目录并尝试：


mvn清洁包装

你会看到“target / my-webapp.war”被构建，所有的正常步骤都被执行了。

###如何一次构建多个项目？

处理多个模块的概念内置于Maven。在本节中，我们将展示如何构建上述的WAR，并在一步中包括以前的JAR。

首先，我们需要在另外两个目录中添加一个父`pom.xml`文件，所以它应该是这样的：


+ - pom.xml
+ - 我的应用程式
| + - pom.xml
{0}{1}src{/1}{/0} :
主要
```java
+ - 我的webapp
| + - pom.xml
{0}{1}src{/1}{/0} :
主要
Web应用

您将创建的POM文件应包含以下内容：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
<modelversion> 4.0.0 </ modelversion>

<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的>应用</ artifactId的>
<版本> 1.0-SNAPSHOT </版本>
<包装> POM </包装>

</modules{0}>{/0}
<模块> MY-应用</模块>
<模块> MY-web应用</模块>
</modules{0}>{/0}
<project>

我们需要从webapp对JAR的依赖，所以将它添加到`my-webapp / pom.xml`中：


1927
<依赖性>
<dependency>
<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的> MY-应用</ artifactId的>
<版本> 1.0-SNAPSHOT </版本>
<dependency>

</依赖>

最后，在子目录中的其他`pom.xml`文件中添加以下`<parent>`元素：


<project xmlns =“http://maven.apache.org/POM/4.0.0”xmlns：xsi =“http://www.w3.org/2001/XMLSchema-instance”xsi：schemalocation =“http：/ /maven.apache.org/POM/4.0.0
http://maven.apache.org/xsd/maven-4.0.0.xsd“>
<母体>
<GROUPID> com.mycompany.app </ GROUPID>
<artifactId的>应用</ artifactId的>
<版本> 1.0-SNAPSHOT </版本>
</父>


现在，尝试从顶级目录运行：


mvn clean install

WAR现在已经在`my-webapp / target / my-webapp.war'中创建，并且包括JAR：


$ jar tvf my-webapp / target / my-webapp-1.0-SNAPSHOT.war
0 Fri Jun 24 10:59:56 EST 2005 META-INF /
222 Fri Jun 24 10:59:54 EST 2005 META-INF / MANIFEST.MF
0 Fri Jun 24 10:59:56 EST 2005 META-INF / maven /
0 Fri Jun 24 10:59:56 EST 2005 META-INF / maven / com.mycompany.app /
0 Fri Jun 24 10:59:56 EST 2005 META-INF / maven / com.mycompany.app / my-webapp /
3239 Fri Jun 24 10:59:56 EST 2005 META-INF / maven / com.mycompany.app / my-webapp / pom.xml
0 Fri Jun 24 10:59:56 EST 2005 WEB-INF /
215 Fri Jun 24 10:59:56 EST 2005 WEB-INF / web.xml
123 Fri Jun 24 10:59:56 EST 2005 META-INF / maven / com.mycompany.app / my-webapp / pom.properties
52 Fri Jun 24 10:59:56 EST 2005 index.jsp
0 Fri Jun 24 10:59:56 EST 2005 WEB-INF / lib /
2713 Fri Jun 24 10:59:56 EST 2005 WEB-INF / lib / my-app-1.0-SNAPSHOT.jar

这是怎么做到的呢？首先，父POM创建（称为“app”）包含“pom”和定义的模块列表。这告诉Maven运行所有的操作，而不是仅仅在当前的项目中（为了覆盖这个行为，你可以使用`\ - non-recursive`命令行选项）。

接下来，我们告诉WAR它需要“我的应用程序”JAR。这做了一些事情：它使它在类路径中可用于WAR中的任何代码（在这种情况下无），它确保JAR始终在WAR之前构建，并且它向WAR插件指示将JAR包括在其库目录。

你可能已经注意到`junit-4.11.jar`是一个依赖关系，但没有结束于WAR。原因是`<scope> test </ scope>`元素 - 它只需要进行测试，因此编译时依赖关系“my-app”不包含在Web应用程序中。

最后一步是包括父定义。这与您可能从Maven 1.0熟悉的`extend`元素不同：这样可以确保POM始终可以被定位，即使项目通过在存储库中查找而与其父代分开分发。

与Maven 1.0不同，您不需要运行`install`来成功执行这些步骤 - 您可以自行运行`package`，并且将从目标目录而不是本地存储库使用反应器中的工件。

您可能希望从顶级目录再次生成您的IDEA工作区


mvn想法：想法



Apache软件基金会 版权所有 2013版权所有。

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
[20]: https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html "Maven in 5 Minutes"
[21]: https://maven.apache.org#
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
[57]: https://maven.apache.org/download.html
[58]: https://maven.apache.org/index.html#What_is_Maven
[59]: https://maven.apache.org/index.html#How_can_Maven_benefit_my_development_process
[60]: https://maven.apache.org/index.html#How_do_I_setup_Maven
[61]: https://maven.apache.org/index.html#How_do_I_make_my_first_Maven_project
[62]: https://maven.apache.org/index.html#How_do_I_compile_my_application_sources
[63]: https://maven.apache.org/index.html#How_do_I_compile_my_test_sources_and_run_my_unit_tests
[64]: https://maven.apache.org/index.html#How_do_I_create_a_JAR_and_install_it_in_my_local_repository
[65]: https://maven.apache.org/index.html#What_is_a_SNAPSHOT_version
[66]: https://maven.apache.org/index.html#How_do_I_use_plugins
[67]: https://maven.apache.org/index.html#How_do_I_add_resources_to_my_JAR
[68]: https://maven.apache.org/index.html#How_do_I_filter_resource_files
[69]: https://maven.apache.org/index.html#How_do_I_use_external_dependencies
[70]: https://maven.apache.org/index.html#How_do_I_deploy_my_jar_in_my_remote_repository
[71]: https://maven.apache.org/index.html#How_do_I_create_documentation
[72]: https://maven.apache.org/index.html#How_do_I_build_other_types_of_projects
[73]: https://maven.apache.org/index.html#How_do_I_build_more_than_one_project_at_once
[74]: https://maven.apache.org/background/philosophy-of-maven.html
[75]: https://maven.apache.org/background/history-of-maven.html
[76]: https://maven.apache.org/mini/guide-configuring-maven.html
[77]: https://maven.apache.org/introduction/introduction-to-archetypes.html
[78]: https://maven.apache.org/introduction/introduction-to-the-pom.html
[79]: https://maven.apache.org/ref/current/maven-model/maven.html
[80]: https://maven.apache.org/introduction/introduction-to-the-standard-directory-layout.html
[81]: http://ant.apache.org
[82]: https://maven.apache.org/ant/build-a1.xml
[83]: https://maven.apache.org/introduction/introduction-to-repositories.html
[84]: https://maven.apache.org/plugins/maven-release-plugin/
[85]: https://maven.apache.org/introduction/introduction-to-the-lifecycle.html
[86]: https://maven.apache.org/plugins/
[87]: https://maven.apache.org/mini/guide-configuring-plugins.html
[88]: https://maven.apache.org/introduction/introduction-to-dependency-mechanism.html
[89]: https://maven.apache.org#How_do_I_create_a_JAR_and_install_it_in_my_local_repository
[90]: https://maven.apache.org/mini/guide-encryption.html
[91]: https://maven.apache.org/mini/guide-site.html
[92]: https://www.apache.org/

  </project></parent></packaging></http:></property></project></local-repository></dir></dir></dir></dir></dir></dir></extension></version></artifactid>
