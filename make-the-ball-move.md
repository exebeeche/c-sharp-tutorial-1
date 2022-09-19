
# Make the ball move

In this article, you create a movement logic for the ball. You have already the form with the layout and the library with the ball. On this step, you need to use only the _ball.cs_ file to write the code.

## Prerequisites

This article builds on the previous one, [Create a ball](create-a-ball.md). If you haven't read that article, go through that one first.

## Add position variables

1. Right after the **OnPaint(PaintEventArgs e)** class, add the following code to declare the variables.

```
		int dx;
        int dy;
```

	- `dx` is the X position.
	- `dy` is the Y position.

2. Add the following code to initiate the ball position.

```
		public void Init(int left, int top, int dx, int dy)
        
        {
            Left = left;
            Top = top;
            this.dx = dx;
            this.dy = dy;
        }
        public enum Direction
        {
            Left, Right, Top, Bottom
        }
```

	In this code sample, the **Init** method initiates the ball position variables and declares them. Also, the [Enum](https://learn.microsoft.com/en-us/dotnet/api/system.enum) class provides the **Direction** enumeration.

3. Add the following code to create the properties about current direction.

```
		public Direction CurrentDirectionX { get; private set; }
        public Direction CurrentDirectionY { get; private set; }
```

	In this code sample, `CurrentDirectionX` and `CurrentDirectionY` properties have `get` and `set` accessors to read and write values of the properties.

4. Add the following code to set the speed property and check if speed has a negative value.

```
		private int speed;
        public int Speed
        {
            get => speed;
            set
            {
                OnSpeedChanged(value);
            }
        }
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

	In this code sample, declare the `speed` variable. Then declare the `Speed` property with `get` and `set` accessors. The `get` accessor reads the `speed` value. The `set` accessor uses the `OnSpeedChanged` method that checks the speed value that is not negative. The `OnSpeedChanged` method also assigns the `speed` value to the `dx` and `dy` variables. ???

5. Add the following code sample to install the counter and update the ball position.

```
		public int Counter { get; private set; }

        public event Action<Direction, Direction, Direction, Direction> OnCollision;
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

	In this code sample, declare the `Counter` property with `get` and `set` accessors. Then declare the `OnCollision` event that reacts on the direction change. The `UpdatePosition` method contains a few checks:
	
	- If the left position of the ball is less or equal than zero, or left position of the ball is more or equal the panel width, than the `Counter` increments.
	
	- If the top position of the ball is less or equal than zero, or top position of the ball is more or equal the panel height, than the `Counter` increments again.
	
	Each check means the ball hits the panel boundry. At this moment, the `OnCollision` event is invoked, and the direction is inverted. Then, the `CurrentDirectionX` and `CurrentDirectionY` variables of the ball position are checked, and the ball position is updated. 
	
## Run your app

On this step, you can run your app and check if everything is good.

1. Press **Ctrl** + **Shift** + **S** or click the  icon to save all files in the project.
2. Press **F5** or click the  icon to run your project.
 
## Next steps

- [Add balls to the form](add-balls-to-the-form.md)
- [Save and run the game](save-and-run-the-game.md)





