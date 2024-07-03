# ekvip Coding Ninjas Standard - Abstract Object Library 

## Table-Of-Contents

1. [Table Of Contents](#table-of-contents)
2. [Summary](#Summary)
3. [Folder Structure](#folder-structure)
4. [Branches](#branches)
5. [Version Number Format](#version-number-format)
6. [Contribution](#contribution)
7. [Version Log](#version-log)

## Summary

* project description: This is a TwinCAT 3 library project for an abstract object, any Coding Ninja Monkey class should be a derivative of this object. This makes it possible to keep different classes very general like e.g. lists. This project is ported to TwinCAT Build 4026 from [CNM Abstract Object](https://ekv-app-git-p01.ekvip.de/CNMTC3/cnm-abstract-object-lib).
* For required software and tools, visit the confluence page:
* [confluence page](https://ekvip.atlassian.net/wiki/spaces/CNMS/pages/1662124042/CNM+AbstractObject)
* [GitLab project page](https://ekv-app-git-p01.ekvip.de/CNMTC3/cnm-abstract-object-lib)

## Folder-Structure

*   **.\\**
*   **build\\** _contains the actual library files (for other test library contains just some unit tests)_
*   **build\\test\\** _contains the actual test library files_
*   **src\\CNM_AbstractObjectLib\\** _root folder for the libray project_
*   **src\\CNM_AbstactObjectTestLib\\** _root folder project for the unit test library project_
*   **test\\** _root folder project for the unit test project (CI pipeline)_
*   **.gitignore**  _the git ignore file for this project_
*   **.gitattributes** _the git attribute file for the LFS support_
*   **README.md** _the file you read right now_

## Branches

The repository has some branches to allow collaboration on a centralized repository, and give everybody the possibility to orient onself. We've two main branches, we use this two to branch from and merge to.

> **The Main Branches Are:**
> -   **main**  _here are  **only**  our well tested releases_
> -   **develop**  _this is the choice for new features during the normal project work_

### creating Branches

The initial main commit contains the reworked readme.md, .gitignore and .gitattributes files.
We **only** use the Jira project-tasks (only sub tasks) to create branches. You can choose between **feature** and **hotfix** branches in the Jira menu. To create a branch in Jira, choose the task you want to create a branch for and click on **"Create branch"** at the tab **"Development"** in the task view.

Here are two examples:  **feature/FRINST-14-analogvalueprocessing/efro**  (here is Elias Froschauer working on feature analogvalueprocessing in project FRINST) and  **_hotfix/FRINST-15-analogvalueprocessingbug/toel_**  (here is Tino working on a hotfix for the bug in analog value processing after production release). 

### creating Tags
Every time you finish a task and merge a branch back to the develop or master, then you have to fill out the version log here and you've to tag this commit with the prefix ***"version_"*** and the version number.
If you work in a group and the current online version is not the latest master or develop commit, you will need to tag the currently used branch with **"online"**.

## Version-Number-Format

The version number format for this project has following pattern: ***{major release}.{minor release}.{development state}.{maintenance}***. Before the software is deployed to the machine, the major number is zero, if the software is deployed and tested 1st time the major number increase to one.

## Version-Number-Format

The version number format for this project has following pattern: ***{major release}.{minor release}.{development state}.{maintenance}***. Before the software is deployed to the machine, the major number is zero, if the software is deployed and tested 1st time the major number increase to one.

> **Version Number Format Description:**

> -   **major release**  _marks api changes_
> -   **minor release**  _marks functional extensions or changes but api is still compatible_
> -   **build**  _**odd** number is beta state,  **even**  is stable release
> -   **revision**  _shows the number of patches and hotfixes_

Some examples:

-   **0.0.0.0**  _initial commit_
-   **0.3.0.7**  _add some features and some bug fixes, software is still in alpha state_
-   **0.3.2.9**  _two more bug fixes and the software is now in release state_
-   **1.0.4.15**  _the api has been changed, this needs changes in the used software as well_

## Contribution

-   The language of software and software comments is **English** and software documentation is **English**
-   Use **branch** and **tag** **rules** as defined earlier
-   If you extend or change the folder structure, then you have to **update this file**
-   You have to provide a **version description** with a small change log for every version tag within this file in the version log section
-   If you want to merge you software to the master branch, then you have to take care that your software is compiling  **without warnings and errors**.
-   If you edit this file you've to do it in **English** and to use the **markdown** format
-   It is **not** allowed to work in one of the main branches directly
-   It is **only** allowed to work in your own branches (with your ekvip name acronym)
-   Every commit to feature or hotfix branch needs to contain the **Jira task id** before the commit description

## Version-Log

### Versions 

1.	[0.0.0.0](#0.0.0.0)
2.	[1.0.3.1](#1.0.3.1)
2.	[2.0.4.1](#2.0.4.1)
3.	[2.0.4.6](#2.0.4.6)
4.	[2.0.4.7](#2.0.4.7)
5.	[3.0.0.8](#3.0.0.9)

### 0.0.0.0 
_initial commit_

### 1.0.3.1
#### **common library information**
*	Build with TwinCAT version 4024.25 **It's compatible from version 4020**
*	Used TwinCAT libraies:
	*	Tc2_Standard 3.3.3.0
	*	Tc2_System 3.4.25.0
	*	Tc3_Module 3.3.21.0
*	library namespace is *CNM_AbstractObject*
*	library placeholder is *CNM_AbstractObject*
*	libaray category is ekvip|types
#### **changes**
* added new to library
	* types
		* enumerations
			*	`ComparationResult`
		*	aliases
			* `ClassName` 
			* `Hashcode` 
			* `ObjectName` 
	*	interfaces:
		*	`IComparable`
		*	`IComperator`
		*	`IObject`
	*	classes:
		*	`Object` it's an abstract class
	* TwinCAT generated
		*	functions
			*	`F_GetCompany`
			*	`F_GetTitle`
			*	`F_GetVersion`
		*	GVLs
			*	`Global_Version`
* added new library for unit test to ease test implementation
* added example project to see how to use the library

### 2.0.4.1
#### **common library information**
*	Build with TwinCAT version 4024.25 **It's compatible from version 4020**
*	Dependencies
	*	Tc2_System 3.4.25.0
	*	CNM_ReturnTypes 2.0.4.0
*	library namespace is *CNM_AbstractObject*
*	library placeholder is *CNM_AbstractObject*
*	libaray category is ekvip|base|types
#### **changes**
* removed from library
	* types
		* enumerations
			*	`ComparationResult`
* added new to library
	* types
		* enumerations
			*	`ComparationResult`
		*	aliases
			* `ClassName` 
			* `Hashcode` 
			* `ObjectName` 
	*	interfaces:
		*	`ICloneable`
		*	`IComparable`
		*	`IComperator`
* updated at library
	*	interfaces:
		*	`IObject`
	*	classes:
		*	`Object`
	* TwinCAT generated
		*	functions
			*	`F_GetCompany`
			*	`F_GetTitle`
			*	`F_GetVersion`
		*	GVLs
			*	`Global_Version`
* updated library for unit test to ease test implementation
* updated example project to see how to use the library
* added unit test project for the library

### 2.0.4.6
#### **common library information**
*	Build with TwinCAT version 4024.29 **It's compatible from version 4020**
*	Dependencies
	*	Tc2_System 3.4.25.0
	*	CNM_ReturnTypes 2.1.4.0
	*	Tc3_Module 3.3.21.0
*	library namespace is *CNM_AbstractObject*
*	library placeholder is *CNM_AbstractObject*
*	library category is ekvip|base|types
#### **changes**
* bugfix in method `Object.isObjectNull`. Now it checks not if the interface has the value `16#0`, it checks now if it has a valid address

### 2.0.4.7
#### **common library information**
*	Build with TwinCAT version 4024.32 **It's compatible from version 4020**
*	Dependencies
	*	Tc2_System 3.4.25.0
	*	CNM_ReturnTypes 4.0.2.0
	*	Tc3_Module 3.3.21.0
*	library namespace is *CNM_AbstractObject*
*	library placeholder is *CNM_AbstractObject*
*	library category is ekvip|base|types
#### **changes**
*	updated  used CNM_ReturnTypes version

### 3.0.0.9
#### **common library information**
*	Build with TwinCAT version 4024.47 **It's compatible from version 4024**
*	Dependencies
	*	Tc2_System 3.5.3.0
	*	CNM_ReturnTypes 4.0.2.0
	*	Tc3_Module 3.3.23.0
*	library namespace is *CNM_AbstractObject*
*	library placeholder is *CNM_AbstractObject*
*	library category is ekvip|base|types
#### **changes**
*	removed FB_exit and FB_reinit from Object, return type of FB_init from Object changed to BOOL
*	check the validity of objects on stack, too
