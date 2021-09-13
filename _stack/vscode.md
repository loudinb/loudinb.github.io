---
layout: article
title: Visual Studio Code Development Containers
description: Learn how to use Docker and the Visual Studio Code remote containers extension to create containerized development environments.
author: Brian Loudin
date: 2021-09-09 16:40:16
---
Containers enable you to create a highly-isolated development environment and allow you to easily "lift and shift" an application into a cloud environment.  [The Remote - Containers extension][1] for [Visual Studio Code][2] lets you use a [Docker][3] container as a full-featured development environment.

Additionally, the majority of Visual Studio Code (VS Code) extensions can be installed inside the container (the workspace).  The VS Code remote-containers extension gives you great flexibility in customizing your entire tool-chain through containerization.

This article outlines how to get started with VS Code development containers on macOS.  It assumes you are familiar with macOS, VS Code and Docker.  The process on Windows is the same but a bit more complex, mainly due to how Docker operates on Windows.  These instructions are not intended for anyone using a Windows based computer.

##### Prerequisites

* [Docker Desktop][4]
* [VS Code][5]  


##### Installing the remote - containers extension

If not already running, launch VS Code.

1. Bring up the Extensions view by clicking on the Extensions icon in the **Activity Bar** or by running the `View: Extensions` command (**⇧⌘X**).
2. Type `remote` in the search box to filter the Marketplace offerings to extensions with **remote** in the title or supplied metadata. You should see **Remote - Containers** in the list.  

	<img src="{{ site.baseurl }}/assets/img/python-stack/vscode-extensions.png" alt="install extension" width="600px"/>  

3. Select the `Install` button to install the extension.  VS Code will download and install the extension directly from the Marketplace.  Once the installation is complete, the Install button (in the list view) will change to the **Manage** gear button.  
	You should also notice a new status bar.  This is the remote-containers status bar and it will indicate if VS Code is running local or remote.  

	<img src="{{ site.baseurl }}/assets/img/python-stack/remote-container-status-bar.png" alt="remote - status bar" width="110px"/>  
	Clicking the status bar will bring up all available **Remote - Containers** commands.  This is a shortcut to running the `View: Command Palette` command (**⇧⌘P**) and filtering on **remote containers**.

##### Creating the development container

There are many ways to create a development container.  In this tutorial we will create a development container using a pre-defined definition provided by the **Remote - Containers** extension.

4. Use the `File` menu and select `Open...` to launch the macOS file window.  Navigate to the folder you want to use for your project and select `Open`.  *Note: It is recommended that you use an empty folder for the root of your development container.*
5. Add a development container definition to the project by running the `Remote-Containers: Add Development Container Configuration Files...` command from the command palette (**⇧⌘P**).  You are presented with a filterable list of definitions.  
	The definitions displayed come from the [vscode-dev-containers][6] GitHub repository. You can browse the **containers** folder of that repository to see the contents of each definition.
6. Select `Python 3` from the list of definitions.  
	When creating the **Python 3** development container you will be asked to select the Python version and the Node.js version.  When prompted, select `3.9` for the **Python version**  
	and `none` for the **Node.js version**  
	The extension will create a folder named **.devcontainer** along with the dev container configuration files. 
7.  VS Code recognizes that a development container configuration has been added to your project folder and prompts you to **reopen folder to develop in container**.   Select `Reopen in Container` when this prompt appears.  
	It can take some time to open new or modified development containers as Docker must build the image.

##### What's happening under the hood?

The most important thing to understand is that the **Remote - Containers** extension includes a server component which is automatically downloaded and installed into the container by VS Code.  The VS Code client on your local system manages and interacts with the server component running on the (remote) container.  Sequentially what happens is:

1. The docker image is built from the Dockerfile created.  Building the image may take a while, but it will be cached by the Docker build system for future use.
2. VS Code gets the server component and copies it along with its own code into the container, it the users home directory (currently /root ). -- Stage 2 also takes a short time, but we will speed that up in a moment.
3. The project folder is mounted as a Docker volume inside the container, it is shared between the container and the host.
4. The VS Code server is started on the container to run the non-UI elements of VS Code.  The UI on your desktop connects to the server through Docker's networking subsystem using known secure transports. 
  
After opening the folder in the container, the VS Code window will look no different.  However, you should see the remote-containers status bar displays “Dev Container: Python 3”.  This means  the container was opened successfully. If you open an integrated terminal, you’ll notice you appear to be logged in as vscode in the folder /workspaces/.....


##### Understanding the configuration files

As previously stated, VS Code will create a folder named **.devcontainer**.  This folder will contain two configuration files:
*  A **devcontainer.json** file which tells Visual Studio Code tells how to create and access your development container.
* A **Dockerfile** which specifies the build steps for the Docker container.   

The **devcontainer.json** file is highly configurable but you will typically use only a small subset of all available properties for a given development container.   You can think of the **devcontainer.json** file as providing the following:

* The (Docker) container build definition to use.
* How VS Code should interact with the container and local resources.
* The commands VS Code should run inside the container.
* VS Code workspace settings, including (workspace) extensions to install.

The **Dockerfile** is a standard Docker file that contains all of the commands needed to build the image.   You can also use Docker Compose for the container definition, for a single-container definition or a multi-container definition.  This is not a Docker tutorial, so we will not be covering any aspects of the Docker build file.  For more information on Docker and Docker Compose for containers, please read the following from the Visual Studio Code team:
* [Advanced Container Configuration][7]
* [Use Docker Compose][8]

##### Full list of resources referenced
* [Developing Inside a Container][9]
* [Advanced Container Configuration][10]
* [Use Docker Compose][11]
* [devcontainer.json reference][12]
* [User and Workspace Settings][13]

**Software Stack**  
macOS: 12.0 beta (21A5506j)
Docker Desktop: 4.0.0 (67817)
Visual Studio Code: 1.60.0 (Universal)
Remote - Containers Extension: v0.194.0


##### Recommended the configuration files

Other tutorials:
1. Linter and Formatter
2. Github template repository
3. CI/CD with CircleCI




https://medium.com/swlh/create-a-reproducible-dev-environment-with-vs-code-fd89285644da

[https://sparrow.dev/devcontainers-quickstart/]

[1]:	https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
[2]:	https://code.visualstudio.com
[3]:	https://www.docker.com
[4]:	https://www.docker.com/products/docker-desktop
[5]:	https://code.visualstudio.com/download
[6]:	https://github.com/Microsoft/vscode-dev-containers
[7]:	https://code.visualstudio.com/docs/remote/containers-advanced
[8]:	https://code.visualstudio.com/docs/containers/docker-compose
[9]:	https://code.visualstudio.com/docs/remote/containers
[10]:	https://code.visualstudio.com/docs/remote/containers-advanced
[11]:	https://code.visualstudio.com/docs/containers/docker-compose
[12]:	https://code.visualstudio.com/docs/remote/devcontainerjson-reference
[13]:	https://code.visualstudio.com/docs/getstarted/settings
[14]:	https://sparrow.dev/devcontainers-quickstart/