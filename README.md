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

     Press Aceptar and in the solution explorer, we can see the added references. With these references, we can have access to the Revit API documents. We set Copia Local to Falso.

     ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/7731dd67-77fc-4468-88b4-429e7cf62f20)
     ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/fa183e5a-76b1-47e3-8e47-952f555de233)

      ## STEP 3 - Link to the references of the class libraries that will be used.

     we link the following references: **using Autodesk.Revit.DB** and **using Autodesk.Revit.UI**

     ![image](https://github.com/AndresF-SanchezG/MyFirstApplication-IExternalCommand/assets/113924667/3fd9e37e-69e2-4328-98d9-fcabbaf91b76)

     - The word **using** is a reserved word that is required to link references. When using the using statement, you can access the classes, methods, and other types defined within the namespace Autodesk.Revit.DB without having to write the full namespace name every time. For example, instead of writing Autodesk.Revit.DB.Wall, you can simply write Wall.
       
     - **Autodesk.Revit.DB:** It´s a namespace in the RevitAPI that contains several classes related to the Revit model database. It´s not a class itself, else a container of classes.

       Some of the most important classes with Autodesk.Revit.DB include:

        - Document: Represents a Revit document, which is essentially a project model.
          
        - Element: Is the base class for all documents that can exist in a Revit document.
          
        - Wall: Represents a wall in a Revit model.
          
        - Transaction: Represent a trasaction for making changes to the Revit document.
          
        - Filter: Contains classes used for filtering elements in the document.
      
     - **Autodesk.Revit.UI:** This namespace is essential for developers that create custom tools, plugins, or applications that interact directly with the Revit user interface, enabling   
      deeper integration and a enhanced user experience.
    
       Some of the most important classes with Autodesk.Revit.UI include:

        - External Commands: Classes to define external commands that can be executed from the Revit interface.

        - Dialogs: Methods and classes for display custom dialog boxes in the Revit interface.

        - Ribbon: Classes and methods for adding tabs, panels and custom controls to the Revit Ribbon interface.

        - Events: Events and handlers related to user interaction, such tas elements selection, view changes, etc.

     - **Autodesk.Revit.Attributes:** It's another namespace within the Revit API. This namespace contains attributes used to mark and configure specific behaviors of classes and methods within the Revit API. Attributes in this namespace are important for customizing and configuring how different components interact and behave within a Revit application or plugin..
    
       Some of the most important attributes with Autodesk.Revit.Attributes include:

        - TransactionAttribute: Allows specifying properties of a transaction, such as its name and execution mode.

        - RegenerationAttribute: Controls how graphics and visual representation are regenerated after making changes in the Revit model.

        - Ribbon: Classes and methods for adding tabs, panels and custom controls to the Revit Ribbon interface.

        - TransactionModeAttribute: Defines the transaction mode for a specific operation, such as automatic or manual.


      ## STEP 4 - Implement the IExternalCommand interface

     To implement the interface, we place a colon next to class and the name of the interface, then we call the methods required by the interface, in this case, the execute method that return a value of type Result.

     ![image](https://github.com/user-attachments/assets/9081308d-5eb0-4027-8323-0e6bbe50244a)

     ## STEP 5 - Write Code
     
     This code defines a simple command external for revit that, when executed, displays a dialog box with a message and return a result indicating that the command was successfully executed.

     ![image](https://github.com/user-attachments/assets/9a5a9b1a-229a-43eb-a5f2-65e8a598bbe2)

     **Namespace:** Defines a namespace called RevitAPP. The namespaces are used to organize code and avoid conflicts between classes from different libraries.

     **public class Class1 : IExternalCommand** Declares a public class called Class1 to implements the IExternalcommand interface. This interface is part of the Revit API and is used to define external commands that can be executed within Revit.

     **Result Execute:** Defines the Execute method, which is required by the IExternalCommand interface. This method is executed when the external command is invoked in Revit. This method return valor of type Result.

     **ExternalCommandData commandData:** ExternalCommandData commandData: Provides information about the environment in which the command is being executed, such as the current Revit document and the application.

     **ref string message** A reference parameter that can be used to return a message to the user if the command execution fails.

     **ElementSet elements** ElementSet elements: A collection of Revit elements that can be manipulated or referenced during the execution of the command.

     **TaskDialog.Show("Titulo", "Mi primera APP con Revit y C#"):** Displays a task dialog in Revit with the title 'Titulo' and the message 'Mi primera APP con Revit y C#'. TaskDialog is a class in the Revit API used to show message dialogs to the user.

     **return Result.Succeeded** Returns Result.Succeeded, indicating that the command executed successfully. Result is an enumeration in the Revit API that defines possible outcomes of executing an external command (Succeeded, Failed, Cancelled).

      ## STEP 5 - Transaction Modes

     Transactions are Revit´s way of protecting the modifications that we can make within projects. Throught transactions, we can make canges to our Revit file and also revert them.
     In Revit, transactions can be configured with different modes that affect how changes and model regeneration are managed. The two specific modes you mentioned are  'Transaction Manual' and 'Transaction Only,' have distinct purposes and behaviors.

     **Transaction Manual:** The manual mode allows the developer explicit control over when to start and finish transactions, as well as when the Revit model should be regenerated. This mode is useful when making multiple changes that should not be regenerated immediately, which can improve performance.

     **Transaction Only** : The 'Transaction Only' mode indicates that the operations performed within this transaction should only be executed if the transaction is successfully completed. This mode ensures that changes are atomic but does not provide control over manual model regeneration.

     In this case, we will use Transaction Manual.

     ![image](https://github.com/user-attachments/assets/6671c00b-dfe9-409c-91cf-d706ca404ef6)

     Once we have our application code ready, we proceed to compile the solution to generate the DLL file.

     ![image](https://github.com/user-attachments/assets/cdc6fb29-5706-4e31-a1ea-bb085506981e)

     ## STEP 6 - Generate .addin file
     
     As mentioned earlier, .addin files are used to configure and register plugins in Revit. This file consists of various tags that perform specific actions. Below is a template of tags, but there are many more that can be studied in the Revit API documentation.

     ![image](https://github.com/user-attachments/assets/2ed3fd96-7815-456c-b22f-0ae8c0756452)

     In this case, the tags to be used were:

     ![image](https://github.com/user-attachments/assets/b7cad738-ae90-4d80-b159-4aa00b32385d)

     Once we have the tags defined, we change the file extension from .txt to .addin.

     ![image](https://github.com/user-attachments/assets/39f77619-5975-493d-9393-bb777a1cb344)

      ## STEP 7 - Link the .dll and .addin files
     
     To link the .dll and .addin files, copy the files to the following paths:

     C:\Users\Andres Sanchez\AppData\Roaming\Autodesk\Revit\Addins\2024

     C:\ProgramData\Autodesk\Revit\Addins\2024

     ![image](https://github.com/user-attachments/assets/6e7613b1-a2e3-4de1-b223-80594feb9441)

     ![image](https://github.com/user-attachments/assets/9a3c1e17-4974-4f64-8a7f-3a37cf41d3a3)




     



     

     

     

     






    
 


    





