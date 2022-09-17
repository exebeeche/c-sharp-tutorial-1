
# Create a ball

In this article, you create a custom UserControl element inside of an external library. It is the best way to reuse this custom UserControl element in future projects.

## Prerequisites

This article builds on the previous one, [Create your Windows Forms project](create-your-windows-forms-project.md). If you haven't read that article, go through that one first.

## Create an external library

1. Right-click the solution in **Solution Explorer** in the right part of the Visual Studio and select **Add > New Project**.

2. On the **Add a new project** page, choose _C#_ in the **All languages** list, _Windows_ in the **All platforms** list, and _Desktop_ in the **All project types** list. Select the **Windows Forms Control Library** template, and then choose **Next**.

3. On the **Configure your new project** page, enter the **Ball** in the **Project name** box, and then click **Next**.

4. On the **Additional information** page, select the **.NET 6 (Long-term support)**, and then click **Create**.

5. Visual Studio creates the **Ball** library inside of your app. This library is located in the **Solution Explorer**. By default, you can see the **UserControl** form on the Visual Studio.

6. Rename the main _.cs_ file to the _ball.cs_ in the **Solution Explorer**.

7. Double-click [PictureBox](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.label) in the **Toolbox** or drag it to the form. Move the control to the upper-left corner of the form. Resize the form to the **PictureBox** size.

## Add the Ball library to the Toolbox of the form

Now you need to add dependencies of the Ball library to your project.

1. Build the **Ball** library before adding the dependency into the app. Select **Build > Build Ball** or press **Ctrl** + **B**.

2. Select the **References** category in the **Solution Explorer** of your app, right-click, and select the **Add Reference**.

3. Select the **Projects** category, check the **Ball**, and click **OK**.

4. Go to the design file of the form and you can see the Ball elementin the **Toolbox**.

## Draw a ball




 