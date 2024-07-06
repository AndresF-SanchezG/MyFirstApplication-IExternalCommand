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

