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

  **Default References:** These are essential elements in application development, as they allow the project to use code and resources that are not within it.

  ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/7154ac33-4b18-4198-a7ac-a5cb0799f65e)

  **Namespace:** The namespace is used to organize and group related classes. In this case RevitAPP can contain all classes and types related to the application.

  **The class class1:** Is a starting point to defining the specific functionality that you want to add to your Revit application. You can add methods, properties, and others members to this class as needed to develop your application.

  ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/2a50ad86-b97a-4187-b141-a8d5295f6799)

  **Solution Explorer:** The explorer solution is a window within Visual Studio Code that allow you to view and manage the files´s and resources´s project of your solution in a structured manner.

  ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/2272a4b7-c21c-4ed0-a23e-82bcbc8eedfe)

  ## STEP 2 - Add Revit references

  To add the references that allow us connect with the Revit API files, we must:

   - Right Click on Referencias and select Agregar referencia.

   ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/05a8a1c5-4548-40cc-a864-8c24cdfe16ff)

   - In the Reference Manager, select **Examinar.** This will open a file explorer where we need to navigate to the following path: **C:\Program Files\Autodesk\Revit 2024**.In this path, we select the following files: **RevitAPI.dll** and **RevitAPIUI.dll.**
     

     ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/eac18fe8-e9c0-48f2-8ca7-498642c83b46)
     ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/a3f9794a-5cc8-460e-8df7-5a6016829cec)

     Press Aceptar and in the solution explorer, we can see the added references. With these references, we can have access to the Revit API documents.

     ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/7731dd67-77fc-4468-88b4-429e7cf62f20)




    
 


    





