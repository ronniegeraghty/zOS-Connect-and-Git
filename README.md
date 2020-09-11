# Using Git with you z/OS Connect EE Projects <!-- omit in toc -->

### Introduction

This tutorial walks through how to work with the Git source code management tool in your z/OS Connect EE projects. You'll learn some of the best practices for organizing your z/OS Connect EE project in a git repository and how to use git to manage changes to your projects.

This work is being done as part of a series of code patterns and tutorials centered on bringing DevOps practices to z/OS Connect EE projects.

### Prerequisites:

- IBM Explorer for z/OS must be installed, or any other IBM Eclipse based editor. If it is not installed please reference this guide on doing so: [Installing IBM Explorer for z/OS Aqua](https://www.ibm.com/support/knowledgecenter/en/SSBDYH_3.2/com.ibm.zexpl.install.client.doc/topics/install20.html)
- The EGit plugin for Eclipse. If you do not have the plugin installed you can follow the instructions in our other code pattern in this series that goes over how to install the plugin and work with git using the plugin. [EGit Installation for IBM Explorer for z/OS]() _Link needs to be added once the code pattern is published_
- The z/OS Connect EE Perspective. If the z/OS Connect EE Perspective is not install on your copy of IBM Explorer for z/OS then please refer to this guide on doing so: [Installing z/OS Explorer and the z/OS Connect EE API toolkit](https://www.ibm.com/support/knowledgecenter/SS4SVW_beta/installing/install_explorer.html)
- A GitHub account. If you don't already have a GitHub account, you can [create a GitHub account here.](https://github.com/join)

### Estimated time

_TBD once code pattern is finished_

### Questions

If you have any questions, feel free to leave an Issue on this GitHub repository.

### Steps: <!-- omit in toc -->

- [1. Set Up](#1-set-up)
- [2. Navigating the z/OS Connect EE Perspective](#2-navigating-the-zos-connect-ee-perspective)
- [3. Repository Organization best practices](#3-repository-organization-best-practices)
- [4. Working with Git](#4-working-with-git)

## 1. Set Up

- **1.1 Fork This Repository:** Click the **Fork** button at the top of this GitHub Repository. This will create a GitHub repositroy under your own account identical to this one. This will give you permission to make changes to the repo.
  ![Fork Repo Button](docs/images/1.1-ForkRepo.png)

- **1.2 Clone the Repository:** Once the fork has finished, Click the green **Clone or download** button. Then, in the drop down, click the **clipboard** button to copy the link to your GitHub repositroy.
  ![Copy Clone Link](docs/images/1.2-CopyCloneLink.png)

- **1.3 Open your Editor:** Now open IBM Explorer for z/OS, or any other IBM Eclipse based editor, like IBM Deverloper for z/OS (IDz).
- **1.4 Navigate to the Git Perspective:** Once your Eclipse editor is open, navigated to the Git Perspective by clicking the **Window** tab, then click **Perspective** >> **Open Perspective** >> **Other...**
  ![Open Perspective Menu](docs/images/1.4-OpenPerspectiveMenu.png)

- **1.5 Select Git Perspective:** In the dropdown select **Git**, then click **OK**. ![Select Git](docs/images/1.5-SelectGit.png)
- **1.6 Clone Repo:** Once the Git Perspective opens up, Click the **Clone a Git repository** button. _Either of the buttons shown in the picture below will work._![Clone Repo Link](docs/images/1.6-CloneRepoLink.png)
- **1.7 Enter Repository Info:** In the pop-up window paste the link we copied off your GitHub repository into the **URI:** field. The **Host:** and **Repository path:** fields should auto completed based on the URI you entered. Enter your GitHub username and password in the **Authentication** section at the bottom of the window, then click the **Next >** button.![Enter URI](docs/images/1.7-EnterURI.png)
- **1.8 Select a Branch:** Make sure that the checkbox next to the **master** option is checked. Then click **Next >**. ![Select Branch](docs/images/1.8-SelectBranch.png)
- **1.9 Finish Cloning:** In the next window, leave the default options and click the **Finish** button. ![Finish Cloning](docs/images/1.9-FinishCloning.png)
- **1.10 Examine Repository:** You should now see your repository in the **Git Repositories** view. Click the dropdown arrow to the left of the repository. Then click the dropdown arror next to the **Working Tree** section. _Note: The working tree shows the files and directories in the git repository._![Examine Repo](docs/images/1.10-ExamineRepo.png)
- **1.11 Import Project:** Right click on **Working Tree**, then click **Import Projects...**![Import Project](docs/images/1.11-ImportProject.png)
- **1.12 Click Archive:** In the pop-up window, click the **Archive...** button at the top right.![Click Archive](docs/images/1.12-ClickArchive.png)
- **1.13 Select the Zip File:** In the file explorer that opens, select the zip file that was included in the repository you cloned down. Then click the **Open** button.![Select Zip File](docs/images/1.13-SelectZipFile.png)
- **1.14 Select Eclipse Project:** In the next pop-up window, select the option that has **Eclipse project** under the **Import as** section. _Optionally_ you can add a working set in the **Working Sets** section at the bottom of the window, but this is not needed. When done click the **Finish** button. ![Select Eclipse Project](docs/images/1.14-SelectEclipseProject.png)
- **1.15 Switch to z/OS Connect EE Perspective:** At the top of IBM Explorer for z/OS, click **Window** -> **Perspective** -> **Open Perspective** -> **Other...**![OpenZOSConnetPerspecitve](docs/images/1.15-OpenZOSConnectPerspective.png)
- **1.16 Select z/OS Connect EE Perspective:** Select **zOS Connect Enterprise Edition**, then click the **OK** button. ![SelectZOSConnectPerspecitve](docs/images/1.16-SelectZOSConnectPerspective.png)
- **1.17 Project Explorer:** Once the z/OS Connect Enterprise Edition Perspective opens up, you should see the project we imported in the **Project Explorer** view on the left. If you expand all the directories in the project it should look like the picture below.![Project Explorer](docs/images/1.17-ProjectExplorer.png)

## 2. Navigating the z/OS Connect EE Perspective

In this section we'll explain some of the different view in the z/OS Connect EE Perspective. Each view within the perspective can be minimized, closed and/or moved as needed. To return to the default perspective setup, click **Window** -> **Perspective** -> **Reset Perspective**.

- **2.1 Getting to the z/OS Connect EE Perspective:** You should already be in the z/OS Connect Persepective if you followed steps **1.15** & **1.16**. There is another way to navigate to the z/OS Connect Perspective if you've already opened it and have navigated away. You can click the z/OS Connect EE Icon in the top right. (The z/OS Connect EE Icon looks like an orange ball.) ![z/OS Connection EE Icon](docs/images/2.1.1-zosConnectIcon.png)
- **2.2 The Default Perspective Apperance:** Below is a picture of the default composition of the z/OS Connect Perspective.
  - _Each view(tab) within the perspective can be minimized, closed and/or moved as needed._
  - _To return to the default after making changes, click **Window -> Perspective -> Reset Perspective**._

![The Default Perspective](docs/images/2.2-TheDefaultPerspective.png)

**1\) Shortcuts**

- This is a pictoral menu of perspectives. It does not show all perspective that are available.
- To open a perspective that is not appearing as a shortcut, click the ![Perspective Icon](docs/images/2.2.1-PerspectivesIcon.png) icon and a pop-up menu will appear.

**2\) Toolbar**

- Quick way to lauch some menu options
- The left most icon ![New Project Icon](docs/images/2.2.2-NewProjectIcon.png) opens the pop-up menu to create a new project.

**3\) Project Explorer**

- This is a list of Service and API Projects that have either been created or imported into the toolkit.
- When a project is created, it will appear in this section.
- Projects are organized as folders with subfolders for some elements.
  ![Project Example](docs/images/2.2.3-ProjectExample.png)
- To open a Service for editing, double-click on the sercice.properties file inside the project folder.
- To open an API for editing, double-click on the package.xml file inside the project folder.
- To **deploy** a Service or API, right click on the project folder and choose **z/OS Connect EE -> Deploy**.

**4\) Service/API Editor View**

- When a Service or API configuration file is opened, the contents appear in this section.
  ![API Configuration](docs/images/2.2.4-APIConfiguration.png)
- If any changes have been made an asterisk(\*) will appear in the tab, indicating that the project needs to be saved.

**5\) z/OS Connect EE Servers**

- If you have configured access to a z/OS Connect EE server, then the server will appear in this section.
- This view allows conected users to view Services and APIs that have ben deployed on the server.
- Those with proper access rights (maintained by the z/OS Connect EE Administrator) will be able to start, stop and remove Services and APIs in this view.
- This view also provides access to the SwaggerUI testing tool.
  ![z/OS Connect Servers](docs/images/2.2.5-zOSConnectServers.png)

**6\) Host Connections, etc.**

- Host Connections - list of all the server connections available through the tool.
  - Connections are categorized by system/subsystem (ex. z/OS Connect Enterprise Edition).
  - A host connection must be made to a server before it will aprear in the z/OS Connect Servers view.
- Properties - more information about a selected element
  - Properties data is availbale for Projects, Services and APIs.
  - Data for Services and APIs include the urls for invoking them
- Progress - displays operations data
- Problems - displays problem/error messages and details
  - Good source of information if a project fails to save or deploy

## 3. Repository Organization best practices

## 4. Working with Git
