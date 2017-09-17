[Source](https://www.eclipse.org/che/docs/ "Permalink to Eclipse Che | introduction")
[Local](https://xy2401.github.io/excerpt/eclipse/che-introduction)
[机翻](https://xy2401.github.io/excerpt/eclipse/che-introduction-zh)
Introduction |  引言

#简介

Eclipse Che提供：

* 包含运行时和IDE的工作区
* RESTful工作区服务器
* 基于浏览器的IDE
* 语言，框架和工具的插件
* 用于创建插件和程序集的SDK

# 起步

你可以从开始：

* [安装][7]
* [创建托管SaaS帐户][8]

# 工作区模型

Che将工作区定义为项目代码文件及其编辑，构建，运行和调试所需的所有依赖项。在我们的世界中，我们将IDE和开发运行时视为工作区的依赖。这些项目是嵌入的，并随工作区一起运行，无论它们运行。这与经典工作区定义（可能包含项目代码）相比较，但需要开发人员绑定其IDE并使用其笔记本电脑本地主机来提供运行时。

![Docker--CodenvyMeeting.png][71]

每个工作区彼此隔离，并负责管理其中包含的组件的生命周期。工作区包含一个或多个运行时。我们工作空间内的默认运行时间是Docker容器，但这些运行时间可以用其他类型的“机器”替代，这些“机器”具有不同的特性。例如，我们提供一种SSH机器类型，并将很快提供本地机器。Docker作为运行时类型的优点使用户可以使用Dockerfiles定义运行时的内容，然后我们可以动态构建工作空间运行时，而无需学习很多复杂的Docker语法。
![Docker--CodenvyMeeting\(1\).png][72]
![Docker--CodenvyMeeting\(2\).png][73]
 工作区可以有0..n个项目，每个项目映射到0..1远程版本控制存储库，如git，subversion或mercurial。项目被安装到工作空间中，以便它们在工作空间内可用，也可在长期存储中使用。每个项目都有一个“类型”，例如“maven”，当被选中时，它将激活一系列插件，改变工作空间的行为以适应该项目类型。项目可以有不同的类型，并且它们也可以具有作为项目的子部分的重构，这些子部分具有自己的打字和行为。
 ![Docker--CodenvyMeeting\(3\).png][74]
 每个工作区都有自己的私有浏览器IDE托管在其中。由Che提供的浏览器IDE被打包为JavaScript和CSS，但是我们的IDE可以被其他IDE替代。由于每个工作空间都有自己的服务器运行时间，因此每个工作区都可以有一个定制的IDE，其中包含不同的插件。
 ![Docker--CodenvyMeeting\(4\).png][75]
 默认情况下，每个工作区也配置自己的SSH服务器。这允许远程客户端和桌面IDE通过SSH安装到工作区中。通过SSH安装，您可以让像IntelliJ或Eclipse这样的IDE与Che中包含的项目和运行时一起工作。
  ![Docker--CodenvyMeeting\(5\).png][76]
工作区托管在Che服务器中，这是一个用于管理工作区的轻量级运行时。单个服务器可以管理大量的工作空间，这些工作空间本身可能运行在同一主机上也可能不会运行。由于Che工作区运行时具有自己的运行时，每个工作区可以在同一个主机或另一个主机上运行，​​由docker守护进程管理。默认情况下，Che服务器也是Docker容器，它本身可以由compose或Swarm操作。
 ![Docker--CodenvyMeeting\(6\).png][77]
 由于工作空间是具有自己的运行时间的服务器，因此它们是协作和共享的。这允许多个用户同时访问同一个工作空间。每个工作区都有自己独特的URL，允许多用户访问。我们目前在一个单一的工作空间中支持最后一笔写入策略的多个用户。在2016年底之前，我们将使用操作变换进行多光标编辑。
  ![Docker--CodenvyMeeting\(7\).png][78]
  每个工作区都使用JSON数据模型定义，该数据模型包含其项目，运行时，其IDE以及允许Che服务器创建副本的其他必要信息。这允许工作空间从一个位置移动到另一个位置，例如从一个车辆服务器到另一个车辆服务器。您将永远不会有“但它运行在该计算机”的问题。工作区也可以具有内部状态快照并保存在注册表中，因此可以从原始模板创建副本，也可以从包含用户开始使用工作区后进行修改的映像创建副本。
 ![Docker--CodenvyMeeting\(8\).png][79]
  Che服务器和每个工作区都有自己的嵌入式RESTful API。用户仪表板Web应用程序和浏览器IDE完成的所有操作都通过RESTful API完成。您可以使用swagger访问这些API，因为每个服务中都提供了Swagger配置。根据管理员或用户部署的插件，服务器内的API集和每个工作空间动态更改。

# 用户

Che有三种类型的用户：

开发者Che可以安装并用作任何类型的编程语言或框架（如Java和JavaScript）的本地IDE。虽然Che作为服务器运行，但它可以在桌面，服务器或嵌入式设备中运行。您可以使用我们的嵌入式浏览器IDE或您现有的IDE，允许SSH进入车间工作区。
* **产品所有者**。Che提供在其工作空间服务器中托管的API，以管理开发人员活动（如编辑，语法分析，编译，打包和调试）的环境，工作区，项目，模板，堆栈和智能感知。您可以使用Che来托管由Che IDE访问的按需工作区或您的产品团队作者的客户端。例如，SAP使用车间工作区服务器来嵌入其SAP Hana的开发工具。
* **插件提供商**。Che提供了一个SDK来创建和打包修改浏览器IDE，工作区或Che服务器的插件。ISV和工具提供商可以添加新的项目类型，编程语言，工具扩展或应用程序。可以为客户端IDE或服务器端编写Che插件。

Che由Bitnami，Codenvy，SAP，IBM，Serli，Red Hat，Tomitribe和WSO2的工程师支持。[Codenvy] [80]为Che提供了多租户，多用户基础设施，增强了安全性，并可在任何公共或私有云上部署。

# 逻辑架构

![Capture_architecture.PNG][81]
Che是在像Tomcat这样的应用服务器之上运行的工作区服务器。当启动Che服务器时，IDE将作为Web应用程序加载，可通过浏览器访问`http://localhost:8080/`。浏览器从Che服务器将IDE作为单页Web应用程序下载。Web应用程序提供UI组件，如向导，面板，编辑器，菜单，工具栏和对话框。

当用户与Web应用程序交互时，他们将创建编写和调试项目所需的工作区，项目，环境，机器和其他工件。IDE通过与管理和与Workspace Master进行交互的RESTful API与Che通讯。

Che服务器控制工作空间的生命周期。工作区是开发人员可以工作的隔离空间。Che将各种服务注入每个工作区，包括项目，源代码，Che插件，SSH守护程序以及语言服务（如JDT核心Intellisense），为Java语言项目提供重构。工作空间还包含一个同步器，根据工作空间是在本地运行还是远程运行，负责使用长期存储来同步机器内的项目文件。

![Capture2_.PNG][82]

Che将工作区的概念定义为项目，环境和命令的组合。项目是可用作一组文件夹，文件和模块的基本代码单元。一个项目可能被映射为1：1到从其克隆的外部git或者subversion资源库。工作区可能有零个或多个项目。项目有一个项目类型，根据所选择的类型，导致Che启用不同行为的工作区。例如，maven项目类型导致Che将maven和Java插件安装到工作区中。

机器是一个运行时单元，提供一堆软件和一组资源来运行工作区的项目。机器绑定到工作区和项目。Che同步机器中的项目文件。机器由包含应在机器中执行的软件列表的配方定义。Che的默认机器实现是Docker，我们使用Dockerfiles定义不同类型运行时的配方。我们还有一个名为“堆栈”的概念，它们是具有额外元信息的预定义配方。Che提供默认的配方和堆栈，但用户可以自己定义。机器的生命周期由每个车库工作区管理。随着工作区的启动，其底层运行时也是如此。此外，Che可以在机器中安装其他软件，以支持开发人员服务，如Intellisense。例如，如果Java插件由于项目类型而被激活，那么在安装运行JDT服务的计算机内部安装代理程序，然后可以由同步到计算机上的项目访问该代理。

# Extensibility可扩展性

Che提供了一个SDK，用于创建新的扩展，将扩展包装到插件中，并将插件分组到程序集中。组件可以独立执行为新服务器，也可以作为使用包含的安装程序的应用程序安装到桌面上。
![Extensibility.PNG][83]
Che可以修改一些方面。

| 类型 | 描述
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |  
| IDE扩展|修改客户端的外观，面板，编辑器，向导，菜单，工具栏和弹出框。IDE扩展以Java编写，并被转载为作为WAR文件托管在Che服务器上的JavaScript Web应用程序。
|服务器扩展（又名，Worskspace Master）|添加或修改在Che服务器内运行的核心API，用于管理工作区，环境和机器。工作区扩展以Java编写并打包为JAR文件。
|工作区扩展（aka，Workspace Agent）|创建或修改在工作区机器中运行的项目特定的扩展，并具有对项目文件的本地访问。定义机器行为，代码模板，命令指令，脚手架命令和智能感知。Che Java扩展作为工作区代理扩展，被部署到机器中，并从Eclipse运行JDT核心服务，以对远程工作区执行本地智能感知操作。

每个扩展类型是单独打包的，因为它们在组件中的部署方式不同。IDE扩展使用GWT进行转换，以生成跨浏览器JavaScript。此应用程序打包为WAR文件并托管在Che服务器上。

Workspace主扩展部署为Che服务器内的服务。一旦部署，他们将激活新的管理服务，可以控制用户，身份和工作空间。

工作区代理扩展使用Che核心库进行编译，并部署在每个工作区机器内运行的嵌入式Che服务器中。车辆服务器被注入由中央工作站主车服务器创建和控制的机器。该嵌入式服务器托管您的工作区代理扩展，并提供了在车内托管的服务和托管项目的机器之间的通信桥梁。

## 设备

使用桌面IDE开发时，工作空间使用localhost作为构建，运行和调试等进程的执行环境。在云端IDE中，localhost不可用，因此工作区服务器必须生成所需的环境。这些环境必须彼此隔离并且可扩展。我们使用Docker生成包含每个环境所需软件的容器。给每个工作区至少有一个环境，但如果需要，用户可以为每个工作区创建其他环境。每个容器可以安装不同的软件。根据项目类型，Che将不同的软件安装到机器中。例如，Java项目将安装JDK，Git和Maven。当用户在其工作空间内工作时，该容器由Che引导，并且项目的源代码已装入其中。自动完成和“mvn clean install”这样的开发人员操作是在容器内执行的进程。用户可以提供自己的Dockerfiles，Che将构建成图像，扩展开发人员可以注册与项目类型相关联的Dockerfile模板。这允许Che管理潜在的无限数量的环境，同时仍然给用户定制灵活性。

## 包括什么

Che为许多编程语言，构建系统，源代码工具和基础设施提供了大量的插件，包括Java，Maven，Ant，Git，Subversion，JavaScript和Angular。JS。社区正在开发自己的，许多被并入主要的仓库。Che可以安装在支持Docker 1.8+或Java 1.8 - 桌面，服务器或云端的任何操作系统上，并已在Linux，MacOS和Windows上进行了测试。它被许可为EPL 1.0。


[1]: https://www.eclipse.org/docs/index.html
[2]: https://www.eclipse.org/docs/tutorials/multi-machine/index.html
[3]: https://www.eclipse.org/docs/openshift/config/index.html
[4]: https://github.com/eclipse/che-docs/tree/master/src/main
[5]: https://www.eclipse.org/docs/assets/imgs/logo-eclipseche.svg
[6]: https://eclipse.org/che/
[7]: https://www.eclipse.org/docs/setup/getting-started/index.html
[8]: https://www.eclipse.org/docs/setup/getting-started-saas-cloud/index.html
[9]: https://www.eclipse.org/docs/setup/configuration/index.html
[10]: https://www.eclipse.org/docs/setup/managing/index.html
[11]: https://www.eclipse.org/docs/setup/cli/index.html
[12]: https://www.eclipse.org/docs/setup/glossary/index.html
[13]: https://www.eclipse.org/docs/setup/docker/index.html
[14]: https://www.eclipse.org/docs/setup/openshift/index.html
[15]: https://www.eclipse.org/docs/devops/intro/index.html
[16]: https://www.eclipse.org/docs/devops/runtime-stacks/index.html
[17]: https://www.eclipse.org/docs/devops/runtime-recipes/index.html
[18]: https://www.eclipse.org/docs/devops/project-samples/index.html
[19]: https://www.eclipse.org/docs/devops/runtime-machines/index.html
[20]: https://www.eclipse.org/docs/devops/volume-mounts/index.html
[21]: https://www.eclipse.org/docs/devops/ws-agents/index.html
[22]: https://www.eclipse.org/docs/devops/workspaces-data-model/index.html
[23]: https://www.eclipse.org/docs/devops/runtime-stacks-data-model/index.html
[24]: https://www.eclipse.org/docs/devops/project-samples-data-model/index.html
[25]: https://www.eclipse.org/docs/ide/projects/index.html
[26]: https://www.eclipse.org/docs/ide/import-a-project/index.html
[27]: https://www.eclipse.org/docs/ide/ssh/index.html
[28]: https://www.eclipse.org/docs/ide/sync/index.html
[29]: https://www.eclipse.org/docs/ide/editor-settings/index.html
[30]: https://www.eclipse.org/docs/ide/intellisense/index.html
[31]: https://www.eclipse.org/docs/ide/commands/index.html
[32]: https://www.eclipse.org/docs/ide/git-svn/index.html
[33]: https://www.eclipse.org/docs/ide/previews/index.html
[34]: https://www.eclipse.org/docs/ide/build/index.html
[35]: https://www.eclipse.org/docs/ide/run/index.html
[36]: https://www.eclipse.org/docs/ide/sharing/index.html
[37]: https://www.eclipse.org/docs/ide/debug/index.html
[38]: https://www.eclipse.org/docs/ide/docker/index.html
[39]: https://www.eclipse.org/docs/ide/electron/index.html
[40]: https://www.eclipse.org/docs/chedir/getting-started/index.html
[41]: https://www.eclipse.org/docs/chedir/why/index.html
[42]: https://www.eclipse.org/docs/chedir/installation/index.html
[43]: https://www.eclipse.org/docs/chedir/project-setup/index.html
[44]: https://www.eclipse.org/docs/chedir/up-and-down/index.html
[45]: https://www.eclipse.org/docs/chedir/chefiles/index.html
[46]: https://www.eclipse.org/docs/chedir/ssh/index.html
[47]: https://www.eclipse.org/docs/chedir/factories/index.html
[48]: https://www.eclipse.org/docs/factory/getting-started/index.html
[49]: https://www.eclipse.org/docs/factory/creating/index.html
[50]: https://www.eclipse.org/docs/factory/json-reference/index.html
[51]: https://www.eclipse.org/docs/assemblies/intro/index.html
[52]: https://www.eclipse.org/docs/assemblies/archetype/index.html
[53]: https://www.eclipse.org/docs/assemblies/assembly-lifecycle/index.html
[54]: https://www.eclipse.org/docs/assemblies/plugin-lifecycle/index.html
[55]: https://www.eclipse.org/docs/assemblies/sdk-rest-apis/index.html
[56]: https://www.eclipse.org/docs/assemblies/sdk-class-reference/index.html
[57]: https://www.eclipse.org/docs/assemblies/sdk-dependency-injection/index.html
[58]: https://www.eclipse.org/docs/assemblies/sdk-dto/index.html
[59]: https://www.eclipse.org/docs/assemblies/sdk-properties/index.html
[60]: https://www.eclipse.org/docs/assemblies/sdk-code-editors/index.html
[61]: https://www.eclipse.org/docs/assemblies/sdk-embed-htmljs/index.html
[62]: https://www.eclipse.org/docs/assemblies/sdk-project-types/index.html
[63]: https://www.eclipse.org/docs/assemblies/sdk-actions/index.html
[64]: https://www.eclipse.org/docs/assemblies/sdk-services/index.html
[65]: https://www.eclipse.org/docs/assemblies/sdk-parts/index.html
[66]: https://www.eclipse.org/docs/assemblies/sdk-themes/index.html
[67]: https://www.eclipse.org/docs/assemblies/sdk-custom-agents/index.html
[68]: https://www.eclipse.org/docs/assemblies/sdk-language-server-protocol/index.html
[69]: https://www.eclipse.org/docs/assemblies/sdk-workspace/index.html
[70]: https://github.com/codenvy/che-docs/blob/master/src/main/_docs/intro.md
[71]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting.png
[72]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(1).png
[73]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(2).png
[74]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(3).png
[75]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(4).png
[76]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(5).png
[77]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(6).png
[78]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(7).png
[79]: https://www.eclipse.org/che/docs/assets/imgs/Docker--CodenvyMeeting(8).png
[80]: http://codenvy.com
[81]: https://www.eclipse.org/che/docs/assets/imgs/Capture_architecture.PNG
[82]: https://www.eclipse.org/che/docs/assets/imgs/Capture_workspace.PNG
[83]: https://www.eclipse.org/che/docs/assets/imgs/Extensibility.PNG
