[Source](https://www.eclipse.org/che/docs/ "Permalink to Eclipse Che | introduction")
[Local](https://xy2401.github.io/excerpt/eclipse/che-introduction)
[机翻](https://xy2401.github.io/excerpt/eclipse/che-introduction-zh)
Introduction |  引言

# Introduction

Eclipse Che provides:

* Workspaces that include runtimes and IDEs
* RESTful workspace server
* A browser-based IDE
* Plug-ins for languages, framework, and tools
* An SDK for creating plug-ins and assemblies

# Getting Started

You can get started with Che by:

* [Installing it][7]
* [Creating a hosted SaaS account][8]

# Workspace Model

 Che defines the workspace to be the project code files and all of their dependencies necessary to edit, build, run, and debug them. In our world, we treat the IDE and the development runtime as a dependency of the workspace. These items are embedded and included with the workspace, whereever it may run. This compares to classic workspace definitions which may include the project code, but require the developer to bind their IDE and use their laptop localhost to provide a runtime.

![Docker--CodenvyMeeting.png][71]

Each workspace is isolated from one another and is responsible for managing the lifecycle of the components that are contained within it. A workspace contains one or more runtimes. The default runtime within our workspaces are Docker containers, but these runtimes can be replaced with other types of "machines" that offer different characteristics. We, for example, provide an SSH machine type and will soon provide localhost machines. The advantage of Docker as the runtime type allows users to define the contents of their runtime using Dockerfiles, for which we can then dynamically construct workspace runtimes without the user having to learn a lot of complex Docker syntax.
![Docker--CodenvyMeeting\(1\).png][72]
![Docker--CodenvyMeeting\(2\).png][73]
 A workspace can have 0..n projects, with each project mapping to 0..1 remote version control repositories such as git, subversion, or mercurial. Projects are mounted into the workspace, so that they are available both inside of the workspace and also available on long term storage. Each project has a "type", such as "maven", which when selected will activate a series of plugins that alter the behavior of the workspace to accommodate that project type. Projects can have different types and they can also have remodules which are sub-portions of a project that have their own typing and behaviors.
 ![Docker--CodenvyMeeting\(3\).png][74]
 Each workspace has its own private browser IDE hosted within it. The browser IDE provided by Che is packaged as JavaScript and CSS, but our IDE could be replaced with other IDEs. Since each workspace has its own server runtimes, each workspace can have a customized IDE with different plugins packaged within it.
 ![Docker--CodenvyMeeting\(4\).png][75]
 By default, each workspace also configures its own SSH server. This allows remote clients and desktop IDEs to SSH mount into the workspace. By SSH mounting, you can let IDEs like IntelliJ or Eclipse work with the projects and runtimes contained within Che.
 ![Docker--CodenvyMeeting\(5\).png][76]
 Workspaces are hosted in the Che server, which is a lightweight runtime for managing workspaces. A single Che server can manage large volumes of workspaces, which themselves may or may not be running on the same host. Since Che workspace runtimes have their own runtimes, each workspace can be running on the same host or another host, managed by a docker daemon. The Che server is also a Docker container by default, which itself could be operated by compose or Swarm.
 ![Docker--CodenvyMeeting\(6\).png][77]
 Since the workspaces are servers that have their own runtimes, they are collaborative and shareable. This allows multiple users to access the same workspace at the same time. Each workspace has its own unique URL which allows multi-user access. We currently support multiple users within a single workspace on a last-write-wins policy. Before the end of 2016, we'll have multi-cursor editing using an operational transform.
 ![Docker--CodenvyMeeting\(7\).png][78]
 Each workspace is defined with a JSON data model that contains the definition of its projects, its runtimes, its IDE, and other necessary information that allows a Che server to create replicas. This allows workspaces to move from one location to another, such as from one Che server to another Che server. You will never have the "but it runs on that computer" issue again. Workspaces can also have their internal state snapshot and saved in a registry, so replicas can be created from the original template, or from images that contain modifications made after a user started working with the workspace.
 ![Docker--CodenvyMeeting\(8\).png][79]
 Both the Che server and each workspace have their own embedded RESTful APIs. Everything that is done by the user dashboard Web application and the browser IDE is done over RESTful APIs. You can access these APIs using swagger as Swagger configurations are provided within each service. The API set within the server and each workspace dynamically changes based upon the plugins that have been deployed by the admin or the user.

# Users

Che has three types of users:

* **Developers**. Che can be installed and used as a local IDE for any kind of programming language or framework, such as Java and JavaScript. While Che runs as a server, it can be run on a desktop, server, or within an embedded device. You can use Che with our embedded browser IDE or your existing IDE which is allowed to SSH into the Che workspaces.
* **Product Owners**. Che provides APIs hosted within its workspace server to manage environments, workspaces, projects, templates, stacks, and intellisense for developer activities such as editing, syntax analysis, compiling, packaging, and debugging. You can use Che to host on-demand workspaces accessed by the Che IDE or a client that your product team authors. For example, SAP uses the Che workspace server to embed its development tools for SAP Hana.
* **Plug-in Providers**. Che provides a SDK to create and package plug-ins that modify the browser IDE, workspaces, or the Che server. ISVs and tool providers can add new project types, programming languages, tooling extensions, or applications. Che plug-ins can be authored for the client-side IDE or the server-side.

Che is supported by engineers from Bitnami, Codenvy, SAP, IBM, Serli, Red Hat, Tomitribe,and WSO2. [Codenvy][80] provides a multi-tenant, multi-user infrastructure for Che with enhanced security and deployable on any public or private cloud.

# Logical Architecture

![Capture_architecture.PNG][81]
Che is a workspace server that runs on top of an application server like Tomcat. When the Che server is launched, the IDE is loaded as a Web application accessible via a browser at `http://localhost:8080/`. The browser downloads the IDE as a single page web app from the Che server. The Web application provides UI components such as wizards, panels, editors, menus, toolbars, and dialog boxes.

As a user interacts with the Web application, they will create workspaces, projects, environments, machines, and other artifacts necessary to code and debug a project. The IDE communicates with Che over RESTful APIs that manage and interact with a Workspace Master.

The Che server controls the lifecycle of workspaces. Workspaces are isolated spaces where developers can work. Che injects various services into each workspace, including the projects, source code, Che plug-ins, SSH daemon, and language services such as JDT core Intellisense to provide refactoring for Java language projects. The workspace also contains a synchronizer which, depending upon whether the workspace is running locally or remotely, is responsible for synchronizing project files from within the machine with Che long term storage.

![Capture2_.PNG][82]

Che defines the notion of a workspace as the combination of projects, environments, and commands. A project is the fundamental unit of code available as a set of folders, files, and modules. A project may be mapped 1:1 to an external git or subversion repository from which it is cloned. A workspace may have zero or more projects. Projects have a project type which, depending upon the type selected, causes Che to enable the workspace with different behaviors. For example, a maven project type causes Che to install the maven and Java plug-ins into the workspace.

A machine is a runtime unit that provides a stack of software and a set of resources to run the projects of the workspace. The machine is bound to the workspace and to the projects. Che synchronizes the project files within the machine. A machine is defined by a recipe that contains the list of software that should be executing within the machine. The default machine implementation in Che is Docker and we use Dockerfiles to define the recipes for different types of runtimes. We also have a concept called, "stacks" which are pre-defined recipes with additional meta-information. Che provides default recipes and stacks, but users can define their own. The machine's lifecycle is managed by each Che workspace. As the workspace is booted, so is its underlying runtimes. Additionally, Che can install additional software into the machine to enable developer services such as Intellisense. For example, if the Java plug-in is activated because of the project type, Che installs an agent inside of the machine that runs JDT services that are then accessible by the projects synchronized onto the machine.

# Extensibility

Che provides an SDK for authoring new extensions, packaging extensions into plug-ins, and grouping plug-ins into an assembly. An assembly can either be executed stand alone as a new server, or, it can be installed onto desktops as an application using included installers. 
![Extensibility.PNG][83]
There are a number of aspects that can be modified within Che.

| Type                                          | Description                                                                                                                                                                                                                                                                                                                                                                                                                              |  
| --------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |  
| IDE Extension                                 | Modify the look-and-feel, panels, editors, wizards, menus, toolbars, and pop-up boxes of the client. IDE extensions are authored in Java and transpiled into a JavaScript Web application that is hosted on the Che server as a WAR file.                                                                                                                                                                                                |  
| Che Server Extension (aka, Worskspace Master) | Add or modify the core APIs that run within the Che server for managing workspaces, environments and machines. Workspace extensions are authored in Java and packaged as JAR files.                                                                                                                                                                                                                                                      |  
| Workspace Extension (aka, Workspace Agent)    | Create or modify project-specific extensions that run within a workspace machine and have local access to project files. Define machine behaviors, code templates, command instructions, scaffolding commands, and intellisense. The Che Java extension is authored as a workspace agent extension, deployed into the machine, and runs JDT core services from Eclipse to do local intellisense operations against the remote workspace. |  

Each extension type is packaged separately because they are deployed differently into the assembly. IDE extensions are transpiled using GWT to generate a cross-browser JavaScript. This application is packaged as a WAR file and hosted on the Che server.

Workspace master extensions are deployed as services within the Che server. Once deployed, they activate new management services that can control users, identity and workspaces.

Workspace agent extensions are compiled with Che core libraries and also deployed within an embedded Che server that runs inside of each workspace machine. The Che server is injected into machines created and controlled by the central workspace master Che server. This embedded server hosts your workspace agent extensions and provides a communication bridge between the services hosted within Che and the machines that are hosting the project.

## Machines

When you develop with a desktop IDE, the workspace uses localhost as the execution environment for processes like build, run and debug. In a cloud IDE, localhost is not available, so the workspace server must generate the environments that it needs. These environments must be isolated from one another and scalable. We use Docker to generate containers that contain the software needed for each environment. Each workspace is given at least one environment, but users may create additional environments for each workspace if they want. Each container can have different software installed. Che installs different software into the machine based upon the project type. For example, a Java project will have the JDK, Git, and Maven installed. When a user is working within their Workspace, this container is booted by Che and the source code of the project is mounted within it. Developer actions like auto-complete and `mvn clean install` are processes that are executed within the container. Users can provide their own Dockerfiles that Che will build into images and extension developers can register Dockerfile templates associated with a project type. This allows Che to manage a potentially infinite number of environments while still giving users customization flexibility.

# What's Included

Che ships with a large number of plug-ins for many programming languages, build systems, source code tools, and infrastructure including Java, Maven, Ant, Git, Subversion, JavaScript, and Angular.JS. The community is developing their own and many are merged into the main Che repository. Che can be installed on any operating system that supports Docker 1.8+ or Java 1.8 – desktop, server or cloud and has been tested on Linux, MacOS and Windows. It is licensed as EPL 1.0.


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
