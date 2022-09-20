
# Create your Windows Forms project

The first step to building your app is a Windows Forms App project.
In this article, you learn how to create a form and add elements to it.

1. Open [Visual Studio](https://visualstudio.microsoft.com/vs/).

2. On the start window, select **Create&nbsp;a&nbsp;new&nbsp;project**.
   ![](/assets/images/create-a-project1.png)

3. On the **Create&nbsp;a&nbsp;new&nbsp;project** window,
   search for Windows Forms.
   Also, you can use the filters to cut the options list. Choose _C#_ in the **All&nbsp;languages** list,
   _Windows_ in the **All&nbsp;platforms** list,
   and Desktop in the **All&nbsp;project&nbsp;types** list.

5. Select the **Windows&nbsp;Forms&nbsp;App&nbsp;(.NET&nbsp;Framework)**
   template for _C#_, and then click **Next**.
![](/assets/images/create-a-project2.png)

6. In the **Configure your new project** window, name your project _Bouncing 
   balls_, then select **Create**.

<!--![](/Users/exebeeche/sources/c-sharp-tutorial-1/img/create-a-project3.
png)-->

Visual Studio creates a solution for your app.
A solution is a container for all the projects and files that your app needs.

In this step,
Visual Studio displays an empty form in the **Windows&nbsp;Form&nbsp;Designer**.
Now you can continue with properties and layout elements.

## Add form properties

1. In the **Windows&nbsp;Form&nbsp;Designer**, select anywhere in **Form1**.
   The **Properties** window is usually pinned in the lower right of Visual 
   Studio.
   <br>
   This section controls various properties, such as foreground and 
   background color, title text that appears at the top of the form, the 
   size of the form, and many other properties.
   <br>
   If you do not see **Properties**,
   select **View&nbsp;>&nbsp;Properties&nbsp;Window** or press **F4**.

2. Find the **Text** property in the **Properties** window. The **Appearance** category includes the **Text** property. Depending on how the properties list is sorted, you may need to scroll down. Enter the value **Bouncing balls**, and then press **Enter**.
   <br>
   Your form now has the text **Bouncing balls** in its title bar.
   ![](/assets/images/form-settings1.png)

3. Set the size of the form using the **Size** property to 850 pixels wide by 700 pixels tall. To change the form size, select it and drag the handle to resize the form.
   <br>
   You can also resize the form by dragging its edges or dragging the handle 
   until the correct size appears as the **Size** value in the **Properties** window.
   <br>
   The drag handle is a small white square in the lower-right corner of the form.

## Add layout elements

1. Select the **Toolbox** tab on the left side of the Visual Studio.
   If you do not see it,
   select **View&nbsp;>&nbsp;Toolbox** from the menu bar or press 
   **Ctrl+Alt+X**.
   The **Toolbox** tab has a few categories to organize form 
   elements. 
   <br>
   You can use the **All Windows Forms** category or any specific 
   category to select an element. Use drag-and-drop actions to order the 
   categories.

2. Double-click [**Label**](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.label) in the **Toolbox** or drag it to the form. Move the control to the upper-left corner of the form.

3. Double-click [**NumericUpDown**](https://docs.microsoft.
   com/en-us/dotnet/api/system.windows.forms.numericupdown) in the 
   **Toolbox** or drag it to the form. Move the control just below the 
   **Label** control.

4. Double-click [**Panel**](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.panel) in the **Toolbox** or drag it to the form. Move the control just below the **NumericUpDown** control. Set the **Panel** size to 350, 320.

5. Double-click [**ListBox**](https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.listbox) in the **Toolbox** or drag it to the form. Move the control just below the **Panel** control. Set the **ListBox** size to 350, 160.

6. Select anywhere on the form.
   Press **Ctrl**&nbsp;+&nbsp;**A** buttons. You will select all control elements.
   Press **Ctrl**&nbsp;+&nbsp;**C** and then **Ctrl**&nbsp;+&nbsp;**V** buttons.
   Use the arrows icon to move selected elements to the right part of the form.

7. In the end, your form should look like the image below.
   
      ![](/assets/images/layout.png)

!!! note

      In this steps, you may not change other properties of these controls.
      <br>
      You will change the behavior of the controls during the next steps.

## Run your app

In this step, you can already run your app to check all layout elements.

1. Press **Ctrl**&nbsp;+&nbsp;**Shift**&nbsp;+&nbsp;**S** to save all files in the project.
2. Press **F5** to run your project.

## Next steps

- [Create a ball](create-a-ball.md)
- [Make the ball move](make-the-ball-move.md)
- [Add balls to the form](add-balls-to-the-form.md)
- [Save and run the game](save-and-run-the-game.md)
