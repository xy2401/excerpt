[Source](https://www.eclipse.org/che/features/ "Permalink to Eclipse Che | Features")
[Local](https://xy2401.github.io/excerpt/eclipse/che-features)
[机翻](https://xy2401.github.io/excerpt/eclipse/che-features-zh)
Permalink to Eclipse Che | Features | 特性

# Eclipse Che | Features

![Eclipse Che][1]

Eclipse Next-Generation IDE

* # Features
* [Prouduction Runtimes][8]
* ["Dev Mode" your Workspace][9]
* [Use any IDE][10]
* [Team-Based Development][11]
* [Language Server Protocol][12]
* [Debuggers][13]
* [SSH / Terminal][14]
* [Stacks][15]
* [RESTful Workspaces][16]
* [Cloud IDE][17]
* [Multi-Project][18]
* [Commands][19]
* [Previews][20]
* [Light Theme][21]
* [Plug-Ins][22]
* [Open Source][23]
* [Dogfooded With Love][24]
* * *

## Production Runtimes

Eclipse Che works with any Docker container, even Compose multi-container runtimes. Use an image from DockerHub, your own private registry or one of the many that ship with Che. Add agents for SSH, terminal and language services to dev-enable your production images. When stopped, Che workspaces can be snapshotted, saving their state between runs.

Under the hood:

* Docker Runtimes
* Compose Runtimes
* Root Access Terminal
* SSH Access
* Pre-Built and Custom Stacks
* Workspace Snapshots

![][26]

## "Dev Mode" your Workspace

Inject developer services into a workspace with agents for syntax auto-complete, error checking and a debugger. Add intellisense for additional languages with language server agents. Enable root-access terminal and SSH access with the flick of a switch.

Under the hood:

* Language Servers
* Intellisense and Refactoring
* Debuggers
* Workspace Agents
* Intelligent Commands
* Root Access Terminal
* SSH Access

![][27]

## Use any IDE

Start working from any device without installing software by using the built-in Eclipse Che IDE. Or stick with the desktop IDE you love by mounting into the Che workspace. Your choice.

Under the hood:

* Browser IDE
* SSH Access
* Mount-and-Sync Workspace
* Electron Client
* RESTful Workspace APIs

![][28]

## Team-Based Development

Create custom stacks - runtimes based on your production images, but with the tools your devs need. Anyone can quickly create a production-compliant app by building on a team stack, or duplicating a workspace. Sample code can even be added for training or to start people on the right foot.

Under the hood:

* Runtime Stacks
* Team Workspaces
* Project Samples

![][29]

## Language Server Protocol

The [Language Server Protocol][30] was developed by Microsoft, Codenvy, Red Hat and IBM as a common protocol to provide language services including syntax analysis, outlining, and refactoring within the Eclipse Che, or the IDE or editor of their own choice. The protocol can be used between client tools and language servers to integrate features such as auto complete, goto definition, and find all references. Language server is a term being applied to the language intelligence programs that are providing the services.

![][31]

## Debuggers

Che can inject debugging agents into a developer workspace to allow variable watching and substitutions, breakpoints, step into / over and other common debug operations. Debuggers can be associated with stacks or individual workspaces.


![][32]

## SSH / Terminal

Che injects an SSH daemon into workspace machines. Connect your existing IDE - Eclipse if you like - with an SSH sync point. Upload your key pair or have Che generate a new pair for each workspace. You can also access your workspace with Che's browser terminal, giving you root access to workspace machines.


![][33]

## Stacks

A stack is a runtime configuration for a workspace. It contains a runtime recipe, meta information like tags, description, environment name, and security policies. Stacks are displayed within the user dashboard and stack tags are used to filter the project code samples that are available. A stack's recipe is either a Dockerfile or a Docker Compose file that will create a runtime to be embedded into the workspace. You can use any of Che's 30+ built-in stacks or author your own unique stack for your work.

![][34]

## RESTful Workspaces

All Che services are reachable through RESTful APIs. Che exposes APIs for managing the workspace master, and also provides RESTful access to each individual workplace through the workspace agent. The Che workspace master provides workspace orchestration and user management. In each workspace agent is a micro Che server that exposes project-specific APIs. For example, Che has RESTful JDT wrappers to enable 100+ forms of distributed Java intellisense. This Java-specific API is injected as a workspace agent by Che. Programming the API is simple - get started by [browsing our APIs with Swagger][35].


![][36]

## Cloud IDE

A no-installation browser IDE and IOE accessible from any local or remote device. Thin, fast, and beautiful - it's the IDE our own engineers wanted. The IDE is packaged as cross-browser JavaScript and CSS, hosted as resources cached by browsers. Work on multiple workspaces in different browser tabs with each tab consuming ~100MB of RAM. It's a smoother interactive experience that doesn't suffer blockages from thrashing when the workspace is remote.

The tools you expect are there: embedded Orion editor, numerous key bindings, globalized keyboard support, and git / subversion tools including diff.


![][37]

## Multi-Project

Che is a true IDE platform, recognizing projects are bound to a repository and given a type. Project types bestow special behaviors, such as when Che injects the RESTful JDT core into workspace machines when Java projects are added. Workspaces can have multiple projects, each with their own type. Projects can be independently built and run, even though all projects share a common workspace machine. Currently, Che has limited project types for JavaScript, Maven, and 'blank'. [We'll collaborate with the ecosystem][38] to package new types for frameworks, packaging systems and programming languages.


![][39]

## Commands

A command is a process that is injected into a machine. Commands are provided by users, workspaces, or projects. Commands have a type, like projects, which imbue additional behaviors. For example, the maven command type has inherent knowledge of how maven lifecycle phases operate. When executed, a command is translated into a process and injected into a machine, where it can operate against projects or other resources within the machine itself. Commands are context sensitive, allowing a user to execute commands across projects and modules, getting context-specific outcomes.


![][40]

## Previews

Create custom previews that launch files and web pages with the context of your projects and workspaces. Embed preview intelligence inside of commands and workspaces so that logic on how to launch and debug your project travels wherever your workspace goes.


![][41]

## Light Theme

Che, like Yoda, wants to bring balance to the force. Flip a switch and transform the IDE with a dark or light theme.


![][42]

## Plugins

Che is extensible, by customizing built-in plugins or authoring your own extensions. Package plugins with Che core to create new assemblies installable by your user base. You can write IDE, Che server, or workspace agent plugins, with Che injecting the plug-in into the right location at the right time.


![][43]

## Open Source to the Core

Eclipse Che has been developed over 4 years with contributions from Codenvy, eXo Platform, Red Hat, Salesforce, IBM, SAP, Microsoft, Intuit, WSO2, Serli, and open source individuals from China, Brazil, France, Ukraine, Russia, Canada, India, Sri Lanka, and the United States. It is part of the Eclipse Cloud Development top-level project, and ecosystem contributions are open and encouraged.

Please participate, even if only spiritually. There are many ways to get involved including starring the [GitHub repo][44], [submitting issues][45], [writing docs][46], or [contributing plug-ins][47].


![][48]

## Dogfooded With Love

We built the product that we would love to use everyday. To do that you must build what you eat and eat what you built. Love -- and sometimes frustration -- has poured into Che as our engineers weaned off their favorite IDEs to build Che with Che.

![][49]

Copyright © Eclipse Foundation 2017

[1]: https://www.eclipse.org/che/images/logo-eclipseche.svg
[2]: https://www.eclipse.org/che/technology/
[3]: https://www.eclipse.org/che/extend/
[4]: https://www.eclipse.org/che/docs/
[5]: https://medium.com/eclipse-che-blog
[6]: https://www.eclipse.org/che/getting-started/
[7]: https://www.eclipse.org/che/media/
[8]: https://www.eclipse.org#prod-runtimes
[9]: https://www.eclipse.org#dev-mode
[10]: https://www.eclipse.org#any-ide
[11]: https://www.eclipse.org#team
[12]: https://www.eclipse.org#lsp
[13]: https://www.eclipse.org#debuggers
[14]: https://www.eclipse.org#ssh
[15]: https://www.eclipse.org#stacks
[16]: https://www.eclipse.org#restful-workspaces
[17]: https://www.eclipse.org#cloud-ide
[18]: https://www.eclipse.org#multi-project
[19]: https://www.eclipse.org#commands
[20]: https://www.eclipse.org#previews
[21]: https://www.eclipse.org#light-theme
[22]: https://www.eclipse.org#plug-in
[23]: https://www.eclipse.org#open-source
[24]: https://www.eclipse.org#love
[25]: https://www.eclipse.org#top
[26]: https://www.eclipse.org/che/images/features/img-features-a-new-kind-of-workspace.png
[27]: https://www.eclipse.org/che/images/features/img-features-dev-mode.png
[28]: https://www.eclipse.org/che/images/features/img-technology-eclipse-desktop.png
[29]: https://www.eclipse.org/che/images/features/img-features-docker-powered.png
[30]: https://github.com/Microsoft/language-server-protocol
[31]: https://www.eclipse.org/che/images/features/img-features-intellisense-javascript.png
[32]: https://www.eclipse.org/che/images/features/img-features-intellisense-java.png
[33]: https://www.eclipse.org/che/images/features/img-features-ssh-workspaces.png
[34]: https://www.eclipse.org/che/images/features/img-features-stacks.png
[35]: https://www.eclipse.org/che/docs/server/rest-api/index.html
[36]: https://www.eclipse.org/che/images/features/img-features-RESTful.png
[37]: https://www.eclipse.org/che/images/features/img-features-cloud-ide.png
[38]: https://github.com/eclipse/che/blob/master/CONTRIBUTING.md
[39]: https://www.eclipse.org/che/images/features/img-features-multi-project-workspaces.png
[40]: https://www.eclipse.org/che/images/features/img-features-commands.png
[41]: https://www.eclipse.org/che/images/features/img-features-previews.png
[42]: https://www.eclipse.org/che/images/features/img-features-light-theme.png
[43]: https://www.eclipse.org/che/images/features/img-features-plugin-framework.png
[44]: https://github.com/codenvy/che/stargazers
[45]: https://github.com/codenvy/che/issues
[46]: https://github.com/eclipse/che-docs
[47]: https://www.eclipse.org/che/docs/plugins/introduction/index.html
[48]: https://www.eclipse.org/che/images/features/img-features-open-source-core.png
[49]: https://www.eclipse.org/che/images/features/img-features-dogfooded.png
[50]: https://twitter.com/share
[51]: https://www.eclipse.org/che/getting-started/cloud/
[52]: https://www.eclipse.org/che/docs/setup/getting-started/
[53]: https://www.eclipse.org/che/extend/codenvy
[54]: https://www.eclipse.org/che/
[55]: https://www.eclipse.org/che/features/
[56]: https://www.eclipse.org/che/checonf/
[57]: https://github.com/eclipse/che/
[58]: https://www.eclipse.org/che/docs/devops/runtime-stacks/
[59]: https://www.eclipse.org/che/docs/devops/runtime-recipes/
[60]: https://www.eclipse.org/che/docs/devops/project-samples/
[61]: https://www.eclipse.org/che/docs/assemblies/intro/
[62]: https://www.eclipse.org/che/docs/assemblies/plugin-lifecycle/
[63]: https://www.eclipse.org/che/docs/assemblies/sdk-rest-apis/
[64]: https://www.eclipse.org/che/community/
[65]: https://projects.eclipse.org/projects/ecd.che
[66]: https://www.infoq.com/presentations/eclipse-che-eclipsecon-2016
[67]: https://openshift.io/
[68]: https://www.eclipse.org/che/extend/sap/
