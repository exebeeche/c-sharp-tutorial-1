
# Add balls to the form

In this article, you add two balls to the form using the **Form&nbsp;Design** 
window and write a code for bouncing balls using _Form1.cs_ file.
In this step, you need to use _Form1.cs_ file to write the code.

## Prerequisites

This article builds on the previous one,
[Make the ball move](make-the-ball-move.md).
If you haven't read that article, go through that one first.

## Add the timer to the form

1. In your Visual Studio project, select **Form1** Forms Designer.

2. In the **Toolbox**,
   double-click [Timer](https://learn.microsoft.com/en-us/dotnet/api/system.windows.forms.timer) in the **Toolbox** or drag it to the form.
   Timer** usually locates under the form.

3. Select the **Timer** and double-click it. Visual Studio opens _Form1.cs_, and you can view the code behind the form.

## Add the balls to the form

1. In the **Toolbox**, select the ball element and drag it to `panel1`.
   ![](/assets/images/add-balls.png)
2. Drug again the ball element to `panel2`.
3. The `ball1` and `ball2` locate in `panel1` and `panel2` correspondingly.
4. Set preferred colors to these balls using the **ForeColor** of the 
   **Properties**.

## Create the ball list

1. After adding the **Timer**, you can see the code generated by default with Visual Studio.
``` C#
   using System;
   using System.Collections.Generic;
   using System.ComponentModel;
   using System.Data;
   using System.Drawing;
   using System.Linq;
   using System.Text;
   using System.Threading.Tasks;
   using System.Windows.Forms;
    
   namespace WindowsFormsApp10
   {
       public partial class Form1 : Form
       {
           public Form1()
           {
               InitializeComponent();
           }
            
           private void timer1_Tick(object sender, EventArgs e)
           {
            
           }
       }
   }
```

2. Add the following code to add the ball list. In this game, you use two balls. In other games or apps, you can use the ball library and add as many balls as you need.
``` C#
   //Add the ball list and create the method that returns the balls from the list
   private List<ball> balls;
   private List<ball> GetAllBalls()
   {
       CreateOrInitBall("Ball1", listBox1, label1, numericUpDown1, panel1, ball1);
       CreateOrInitBall("Ball2", listBox2, label2, numericUpDown2, panel2, ball2);
       return new List<ball>
       {
           ball1,
           ball2
       };
   }
``` 
   
    In this code sample,
  [List](https://learn.microsoft.com/en-us/dotnet/api/system.collections.generic.list-1)&nbsp;`balls` stores objects from the `ball` class. 

    The `GetAllBalls` method invokes the `CreateOrInitBall` method
  that we will add later.
  Also, the `GetAllBalls` method returns the balls from the list, which were 
   added on the previous step using the **Form1** Forms Designer.

3. Add the following code to initialize the ball list.
``` C#
   public Form1()
   {
       InitializeComponent();
       InitBalls();
   }
   //Initialize the ball list
   private void InitBalls()
   {
       balls = GetAllBalls();
   }
```

4. Add the following code to connect the balls with the speed counter and 
   text field with statistics.
``` C#
   //Create the method that accepts the control elements as balls parameters
   //and sets a dependency between the ball position and the control elements
   private void CreateOrInitBall(string name, ListBox listbox, Label output, NumericUpDown num, Panel parent, Ball ball = null)
   {
       var currentBall = ball ?? new Ball();
       currentBall.Name = name;
    
       if (ball == null)
       {
           parent.Controls.Add(currentBall);
       }
    
       num.ValueChanged += (sender, e) =>
       {
           currentBall.Speed = (int)(sender as NumericUpDown).Value;
       };
    
       currentBall.OnCollision += (oldX, oldY, newX, newY) =>
       {
           output.Text = $"#{currentBall.Name}: {currentBall.Counter} collisions";
           listbox.Items.Add($"{DateTime.Now.ToString("HH:mm:ss")} {oldX}{oldY} => {newX}{newY}");
       };
   }
```

    In this code sample, the `CreateOrInitBall` method uses the following 
  controls:

    - ListBox for the changing direction statistics.
    - Label for the collision number.
    - NumericUpDown for the speed increasing/decreasing.
    - Panel as ball territory.

## Run your app

In this step, you can run your app and check if everything is good.

1. Press **Ctrl**&nbsp;+&nbsp;**Shift**&nbsp;+&nbsp;**S** or click the icon to save all files in the project.
2. Press **F5** or click the icon to run your project.

## Next steps

- [Save and run the game](save-and-run-the-game.md)


