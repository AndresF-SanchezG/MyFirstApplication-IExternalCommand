# MyFirstApplication-IExternalCommand

## Introduction

The Revit Api allows to developers interact and extend the functionalities of the revit Software.
In this exercise we will use IExternalCommnad, which is an integral part of the Revit API. This api provides tools and libraries specifically used to create external command that can be executed within the revit environment.
These commands can be anything, from automating repetitive task to creating new tools that enhance Revit´s functionality.

## Target

The objective of this exercise is to create a custom command in Revit that displays a dialog box with a custom message. 
The title of the dialog box will be "App with Revit and C#" and its message will be "Mi primera APP con Revit y C#"

## Solution

Revit and applications developed in C# communicate through .addin files.
The .addin files are used to register and configure plugins in Revit. These files are essential to Revit recognize, loand and execute custom commands or applications developed in languages such as C#.
The .addin files inform revit about the existence of plugins and where find the .dll files that contain them.

DLL(Dynamic Link Library) are dynamic linking libraries that contain code, data and resources that can be used by multiple programs simultaneously. Instead of embedding all necessary code to perform task within the main executable file (EXE), commom functions are grouped into a DLL file, which is loaded when a program needs to use its functions.

![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/b5cb7679-dba5-4dd6-8493-bb6023cb8c87)

To write the application code, we will use the .NET FRAMEWORK 4.8 development environment, which is the framework used to build the Revit API. This framawork uses languages like C# and VB.NET to interact with Revit.

## STEP 1 - Set up work template

Through of the editor code VISUAL STUDIO CODE we choose the framework 4.8 to use and select a class library template. This template will allow us to access the revit libraries.

![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/c500500a-88ed-4bcf-aea4-b72e05c93f1c)

In this template we find:

  Default References: These are essential elements in application development, as they allow the project to use code and resources that are not within it.

  ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/7154ac33-4b18-4198-a7ac-a5cb0799f65e)

  Namespace: The namespace is used to organize and group related classes. In this case RevitAPP can contain all classes and types related to the application.

  The class clas1: Is a starting point to defining the specific functionality that you want to add to your Revit application. You can add methods, properties, and others members to this class as needed to develop your application.



