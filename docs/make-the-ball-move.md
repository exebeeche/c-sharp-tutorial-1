# Make the ball move

In this article, you create a movement logic for the ball.
You have already the form with the layout and the library with the ball.

In this step, you need to use only the _ball.cs_ file to write the code.

## Prerequisites

This article builds on the previous one, [Create a ball](create-a-ball.md). 
If you have not read that article, go through that one first.

## Add position variables

1. Right after the `OnPaint(PaintEventArgs e)` class, add the following code to declare the variables.
``` C#
   //Declare the variables of the ball position
   int dx;
   int dy;
```

   - `dx` is the X position.
   - `dy` is the Y position.

2. Add the following code to initiate the ball position.
``` C#
//Initiate the ball position
   public void Init(int left, int top, int dx, int dy)
        
   {
       Left = left;
       Top = top;
       this.dx = dx;
       this.dy = dy;
   }
   //Enumerate four directions
   public enum Direction
   {
       Left, Right, Top, Bottom
   }
```
    In this code sample, the **Init** method initiates the ball position 
 variables and declares them.
  Also,
  the [Enum](https://learn.microsoft.com/en-us/dotnet/api/system.enum) class provides the **Direction** enumeration.

3. Add the following code to create the properties of the current direction.
``` C#
   //Create properties of the current direction
   public Direction CurrentDirectionX { get; private set; }
   public Direction CurrentDirectionY { get; private set; }
```
    In this code sample, the `CurrentDirectionX` and `CurrentDirectionY` 
properties have `get` and `set` accessors to read and write the values of the properties.

4. Add the following code to set the speed property and check if speed has a negative value.
``` C#
   //Declare the speed variable and property
   private int speed;
   public int Speed
   {
       get => speed;
       set
       {
           OnSpeedChanged(value);
       }
   }
   //Create the method that checks if the speed value is not negative and assigns 
   //the new values for the `dx` and `dy` variables depending on the `speed` 
   //value.
   private void OnSpeedChanged(int value)
   {
       if (value >= 0)
       {
           speed = value;
           dx = dx != 0 ? dx / Math.Abs(dx) * value : value;
           dy = dy != 0 ? dy / Math.Abs(dy) * value : value;
       }
   }
```
    In this code sample, declare the `speed` variable. Then declare the `Speed` 
 property with `get` and `set` accessors. The `get` accessor reads the `speed` value.
 
    The `set` accessor uses the `OnSpeedChanged` method that checks if the speed value is not negative and assigns 
 the new values for the `dx` and `dy` variables depending on the `speed` value.

5. Add the following code sample to install the counter and update the ball position.
``` C#
   //Declare the Counter property
   public int Counter { get; private set; }
   //Create an action event with four directions
   public event Action<Direction, Direction, Direction, Direction> OnCollision;
   //Create the method that updates the ball position and counts collisions
   public void UpdatePosition()
   {
       if (Left + dx <= 0 || Left + Width + dx >= Parent.Width)
       {
           Counter++;
           OnCollision?.Invoke(CurrentDirectionX, CurrentDirectionY, dx > 0 ? Direction.Right : Direction.Left, CurrentDirectionY);
           dx = -dx;

       }

       if (Top + dy <= 0 || Top + Height + dy >= Parent.Height)
       {
           Counter++;
           OnCollision?.Invoke(CurrentDirectionX, CurrentDirectionY, CurrentDirectionX, dy > 0 ? Direction.Bottom : Direction.Top);
           dy = -dy;
       }

       CurrentDirectionX = dx > 0 ? Direction.Left : Direction.Right;
       CurrentDirectionY = dy > 0 ? Direction.Top : Direction.Bottom;
       Left += dx;
       Top += dy;
   }
```

    In this code sample, declare the `Counter` property with `get` and `set` 
 accessors.
 Then declare the `OnCollision` event that reacts to the direction 
  change.
 The `UpdatePosition` method contains a few checks:
	
    - If the left position of the ball is less or equal to zero, or the left 
   position of the ball is more or equal to the panel width, then the 
    `Counter` increments.
	
    - If the top position of the ball is less or equal to zero, or the top 
    position of the ball is more or equal to the panel height, then the 
    `Counter` increments again.
	
    Each check means the ball hits the panel boundary. At this moment, the 
  `OnCollision` event is invoked, and the direction is inverted. Then, the `CurrentDirectionX` and `CurrentDirectionY` variables of the ball position are checked, and the ball position is updated. 
	
## Run your app

In this step, you can run your app and check if everything is good.

1. Press **Ctrl**&nbsp;+&nbsp;**Shift**&nbsp;+&nbsp;**S** or click the icon to save all files in the project.
2. Press **F5** or click the icon to run your project.
 
## Next steps

- [Add balls to the form](add-balls-to-the-form.md)
- [Save and run the game](save-and-run-the-game.md)





