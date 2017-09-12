[Source](https://www.eclipse.org/che/features/ "Permalink to Eclipse Che | Features")
[Local](https://xy2401.github.io/excerpt/eclipse/che-features)
[机翻](https://xy2401.github.io/excerpt/eclipse/che-features-zh)
Permalink to Eclipse Che | Features | 特性

# Eclipse Che |特征

![Eclipse Che][1]

Eclipse下一代IDE

* # 特征
* [制作运行时] [8]
* [“开发模式”你的工作区] [9]
* [使用任何IDE] [10]
* [团队发展] [11]
* [语言服务器协议] [12]
* [Debuggers] [13]
* [SSH /终端] [14]
* [堆叠] [15]
* [RESTful工作区] [16]
* [Cloud IDE] [17]
* [多项目] [18]
* [命令][19]
* [预览][20]
* [轻主题][21]
* [插件][22]
* [开源][23]
* [爱啃自己家狗粮][24]
* * *

##生产运行时

Eclipse Che可以与任何Docker容器一起工作，甚至可以构建多容器运行时。使用DockerHub的图像，您自己的私人注册表或与Che一起提供的许多注册表。添加SSH，终端和语言服务的代理，以启用生产映像。停止工作时，可以对工作区进行快照，在运行之间保存状态。

Under the Hood

* Docker Runtimes
* 组合运行时
* 根接入终端
* SSH访问
* 预制和定制堆叠
* 工作区快照

![][26]

## “开发模式”你的工作区

将开发人员服务注入到具有用于语法自动完成，错误检查和调试器的代理的工作空间中。使用语言服务器代理添加其他语言的智能感知。启用根访问终端和SSH访问，轻按一个开关。

Under the Hood

* 语言服务器
* 智能感知和重构
* 调试器
* 工作区代理
* 智能命令
* 根接入终端
* SSH访问

![][27]

## 使用任何IDE

通过使用内置的Eclipse Che IDE，可以从任何设备开始工作，而无需安装软件。或者通过安装在车库工作区中来坚持使用您喜欢的桌面IDE。毕竟这都是你自己的选择。

Under the Hood

* 浏览器IDE
* SSH访问
* 安装和同步工作区
* 电子客户端
* RESTful Workspace API

![][28]

## 团队发展

创建自定义堆栈 - 基于您的生产映像的运行时，但使用您的开发人员需要的工具。任何人都可以通过构建团队堆栈或复制工作区来快速创建符合生产要求的应用程序。甚至可以添加示例代码进行培训或者从右脚开始。

Under the Hood

* 运行时栈
* 团队工作区
* 项目样本

![][29]

## 语言服务器协议

[语言服务器协议] [30]由 Microsoft，Codenvy，Red Hat和IBM开发，作为提供语言服务的通用协议，包括Eclipse Che中的语法分析，概述和重构，或者自己选择的IDE或编辑器。该协议可以在客户端工具和语言服务器之间使用，以集成诸如自动完成，goto定义等功能，并查找所有引用。语言服务器是一种适用于提供服务的语言智能程序的术语。

![][31]

## 调试器

Che可以将调试代理程序注入开发人员工作区，以允许变量观察和替换，断点，逐步转换和其他常见的调试操作。调试器可以与堆栈或单个工作空间相关联。


![][32]

## SSH /终端

Che将SSH守护进程注入工作区机器。使用SSH同步点连接现有的IDE  - 如果您愿意的话 -  Eclipse。上传您的密钥对或为每个工作区生成一个新的对。您还可以使用Che的浏览器终端访问您的工作区，从而可以访问工作区机器。




## 堆叠

堆栈是工作空间的运行时配置。它包含运行时配方，标签，描述，环境名称和安全策略等元信息。堆栈显示在用户仪表板中，堆栈标签用于过滤可用的项目代码示例。堆栈的配方是Dockerfile或Docker Compose文件，它将创建一个要嵌入工作区的运行时。您可以使用任何Che的30+内置堆栈或为您的工作创建自己的独特堆栈。

![][34]

## RESTful工作区

所有Che服务都可通过RESTful API访问。 Che公开了用于管理工作区主控的API，并通过工作区代理程序为每个工作场所提供RESTful访问。Che工作区主程序提供工作区编排和用户管理。在每个工作区代理程序中都是一个暴露项目特定API的微型服务器。例如，Che拥有RESTful JDT包装器，可以启用100多种分布式Java智能感知形式。这个Java特定的API作为工作区代理被注入。API的编程很简单 - 通过[使用Swagger浏览我们的API] [35]开始。


![][36]

## Cloud IDE

任何本地或远程设备可以访问的无安装浏览器IDE和IOE。薄，快，美 - 这是我们自己工程师想要的IDE。IDE作为跨浏览器的JavaScript和CSS打包，作为浏览器缓存的资源进行托管。在不同浏览器标签中的多个工作区工作，每个标签消耗大约100MB的RAM。这是一个更平滑的互动体验，当工作空间远程时，它不会受到阻止的冲击。

您期望的工具有:嵌入式Orion编辑器，众多键盘绑定，全球化键盘支持以及git / subversion工具，包括diff。


![][37]

## 多项目

Che是一个真正的IDE平台，认识到项目被绑定到一个存储库并给出一个类型。项目类型提供了特殊的行为，例如在添加Java项目时，将Che将RESTful JDT内核注入工作区机器时。工作区可以有多个项目，每个项目都有自己的类型。项目可以独立构建和运行，即使所有项目共享一个共同的工作空间机器。目前，Che对JavaScript，Maven和“空白”的项目类型有限。[我们将与生态系统合作] [38]为框架，包装系统和编程语言打包新的类型。


![][39]

## 命令

一个命令是一个注入机器的进程。命令由用户，工作区或项目提供。命令有一个类型，像项目，这增加了额外的行为。例如，maven命令类型具有如何运行maven生命周期阶段的内在知识。执行时，将命令转换为进程并注入到机器中，在该机器中可以对机器本身内的项目或其他资源进行操作。命令是上下文敏感的，允许用户在项目和模块之间执行命令，获取上下文相关的结果。


![][40]

## 预览

创建使用项目和工作区上下文启动文件和网页的自定义预览。嵌入命令和工作区内的预览智能，以便如何启动和调试您的项目的逻辑，无论您的工作空间如何。


![][41]

## 轻主题

像Yoda一样，Cheo想要给力量带来平衡。翻转开关，并用黑色或浅色主题转换IDE。


![][41]

## 插件

Che可扩展，通过定制内置插件或创建自己的扩展。使用Che核心的软件包插件来创建可由您的用户群安装的新程序集。您可以编写IDE，Che服务器或工作区代理插件，并在适当的时间将插件插入正确的位置。


![][41]

## 开源到核心

Eclipse Che开发了四年多，来自Codenvy，eXo Platform，Red Hat，Salesforce，IBM，SAP，Microsoft，Intuit，WSO2，Serli以及来自中国，巴西，法国，乌克兰，俄罗斯，加拿大，印度，斯里兰卡和美国。它是Eclipse Cloud Development顶级项目的一部分，生态系统的贡献是开放和鼓励的。

请参加，即使只在精神上。有很多方法可以参与，包括主演[GitHub repo][44]，[提交问题][45]，[撰写文档][46]或[贡献插件][47]。


![][43]

##爱狗爱狗

我们建立了我们每天都喜欢使用的产品。要做到这一点，你必须建立你吃的东西，吃掉你所建造的东西。爱 - 有时是沮丧的 - 已经倾注在车上，因为我们的工程师将他们最喜爱的IDE断掉，用车来搭建车。



版权所有©Eclipse Foundation 2017

[1]:https://www.eclipse.org/che/images/logo-eclipseche.svg
[2]:https://www.eclipse.org/che/technology/
[3]:https://www.eclipse.org/che/extend/
[4]:https://www.eclipse.org/che/docs/
[5]:https://medium.com/eclipse-che-blog
[6]:https://www.eclipse.org/che/getting-started/
[7]:https://www.eclipse.org/che/media/
[8]:https://www.eclipse.org#prod-runtimes
[9]:https://www.eclipse.org#dev-mode
[10]:https://www.eclipse.org#any-ide
[11]:https://www.eclipse.org#team
[12]:https://www.eclipse.org#lsp
[13]:https://www.eclipse.org#debuggers
[14]:https://www.eclipse.org#ssh
[15]:https://www.eclipse.org#stacks
[16]:https://www.eclipse.org#restful-workspaces
[17]:https://www.eclipse.org#cloudide
[18]:https://www.eclipse.org#multi-project
[19]:https://www.eclipse.org#commands
[20]:https://www.eclipse.org#previews
[21]:https://www.eclipse.org#light-theme
[22]:https://www.eclipse.org#plug-in
[23]:https://www.eclipse.org#open-source
[24]:https://www.eclipse.org#love
[25]:https://www.eclipse.org#top
[26]:https://www.eclipse.org/che/images/features/img-features-a-new-kind-of-workspace.png
[27]:https://www.eclipse.org/che/images/features/img-features-dev-mode.png
[28]:https://www.eclipse.org/che/images/features/img-technology-eclipse-desktop.png
[29]:https://www.eclipse.org/che/images/features/img-features-docker-powered.png
[30]:https://github.com/Microsoft/language-server-protocol
[31]:https://www.eclipse.org/che/images/features/img-features-intellisense-javascript.png
[32]:https://www.eclipse.org/che/images/features/img-features-intellisense-java.png
[33]:https://www.eclipse.org/che/images/features/img-features-ssh-workspaces.png
[34]:https://www.eclipse.org/che/images/features/img-features-stacks.png
[35]:https://www.eclipse.org/che/docs/server/rest-api/index.html
[36]:https://www.eclipse.org/che/images/features/img-features-RESTful.png
[37]:https://www.eclipse.org/che/images/features/img-features-cloud-ide.png
[38]:https://github.com/eclipse/che/blob/master/CONTRIBUTING.md
[39]:https://www.eclipse.org/che/images/features/img-features-multi-project-workspaces.png
[40]:https://www.eclipse.org/che/images/features/img-features-commands.png
[41]:https://www.eclipse.org/che/images/features/img-features-previews.png
[42]:https://www.eclipse.org/che/images/features/img-features-light-theme.png
[43]:https://www.eclipse.org/che/images/features/img-features-plugin-framework.png
[44]:https://github.com/codenvy/che/stargazers
[45]:https://github.com/codenvy/che/issues
[46]:https://github.com/eclipse/che-docs
[47]:https://www.eclipse.org/che/docs/plugins/introduction/index.html
[48]:https://www.eclipse.org/che/images/features/img-features-open-source-core.png
[49]:https://www.eclipse.org/che/images/features/img-features-dogfooded.png
[50]:https://twitter.com/share
[51]:https://www.eclipse.org/che/getting-started/cloud/
[52]:https://www.eclipse.org/che/docs/setup/getting-started/
[53]:https://www.eclipse.org/che/extend/codenvy
[54]:https://www.eclipse.org/che/
[55]:https://www.eclipse.org/che/features/
[56]:https://www.eclipse.org/che/checonf/
[57]:https://github.com/eclipse/che/
[58]:https://www.eclipse.org/che/docs/devops/runtime-stacks/
[59]:https://www.eclipse.org/che/docs/devops/runtime-recipes/
[60]:https://www.eclipse.org/che/docs/devops/project-samples/
[61]:https://www.eclipse.org/che/docs/assemblies/intro/
[62]:https://www.eclipse.org/che/docs/assemblies/plugin-lifecycle/
[63]:https://www.eclipse.org/che/docs/assemblies/sdk-rest-apis/
[64]:https://www.eclipse.org/che/community/
[65]:https://projects.eclipse.org/projects/ecd.che
[66]:https://www.infoq.com/presentations/eclipse-che-eclipsecon-2016
[67]:https://openshift.io/
[68]:https://www.eclipse.org/che/extend/sap/
