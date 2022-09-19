
# Create your Windows Forms project

The first step of your app is to create a Windows Forms App project. In this article, you learn how to create a form and elements in it.

1. Open [Visual Studio](https://visualstudio.microsoft.com/vs/).

2. On the start window, select **Create a new project**.

3. On the **Create a new project** window, search for Windows Forms.
   Also, you can use the filters to cut the option list.
   Choose _C#_ in the **All languages** list,
   _Windows_ in the **All platforms** list, and Desktop in the **All project 
   types** list.

4. Select the **Windows Forms App (.NET Framework)** template for _C#_, and 
   then select Next.

5. In the **Configure your new project** window, name your project _Bouncing 
   balls_, then select Create.

Visual Studio creates a solution for your app.
A solution is a container for all the projects and files that your app needs.
At this step, Visual Studio displays an empty form in the **Windows Form Designer**.
Now you can move further with properties and layout elements.

## Add form properties

1. In the **Windows Form Designer**, select anywhere in **Form1**. The **Properties** window is usually pinned in the lower right of Visual Studio. This section controls various properties, such as foreground and background color, title text that appears at the top of the form, the size of the form, and many other properties.

   If you do not see **Properties**, select **View > Properties Window** or press **F4**.

2. Find the **Text** property in the **Properties** window. The **Appearance** category includes the **Text** property. Depending on how the properties list is sorted, you may need to scroll down. Enter the value **Bouncing balls**, and then press **Enter**.

   Your form now has the text **Bouncing balls** in its title bar.

3. To change the form size, select it and drag the handle to resize the form. You can also resize the form by changing the **Size** property.

## Add layout elements

1. Select the **Toolbox** tab on the left side of the Visual Studio. If you do not see it, select **View > Toolbox** from the menu bar or press **Ctrl+Alt+X**.

2. Drag two [Label](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.label?view=windowsdesktop-6.0) controls to the form one by one. Place the controls to the upper-left corner of the form.

3. Drag two [NumericUpDown](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.numericupdown?view=windowsdesktop-6.0) controls to the form one by one. Place the controls to the upper-center part of the form.

4. Drag two [Panel](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.panel?view=windowsdesktop-6.0) controls to the form one by one. Place the controls to the center of the form.

5. Finaly, drag two [TextBox](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.textbox?view=windowsdesktop-6.0) controls to the form one by one. Place the controls to the down-center part of the form.

6. In the end, your form should look like on the image below.



