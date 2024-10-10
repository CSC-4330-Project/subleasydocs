# **HomeProgressIndicator**

## **Constructor**
- **Name:** HomeProgressIndicator
- **Parameters:**
  - `key` (Key?): The widget's key
  - `size` (double): The size of the indicator (default: 50.0)
  - `color` (Color): The color of the indicator (default: Colors.white)
  - `duration` (Duration): The duration of one complete animation cycle (default: 1 second)

**What it does:**
HomeProgressIndicator is a StatefulWidget that creates an animated house-shaped progress indicator.

## **createState**
- **Return type:** HomeProgressIndicatorState

**What it does:**
Creates the mutable state for this widget.

# **HomeProgressIndicatorState**

## **initState**
**What it does:**
Initializes the state of the widget. It creates and configures an AnimationController that repeats indefinitely.

## **dispose**
**What it does:**
Disposes of the AnimationController when the widget is removed from the widget tree.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
Builds the widget tree for the progress indicator. It uses an AnimatedBuilder to rebuild the widget on each animation tick, creating a CustomPaint widget with a HomeProgressPainter.

# **HomeProgressPainter**

## **Constructor**
- **Name:** HomeProgressPainter
- **Parameters:**
  - `progress` (double): The current progress of the animation (0.0 to 1.0)
  - `color` (Color): The color to paint the house outline

**What it does:**
HomeProgressPainter is a CustomPainter that draws the animated house shape.

## **paint**
- **Parameters:**
  - `canvas` (Canvas): The canvas to draw on
  - `size` (Size): The size of the area to draw in
- **Return type:** void

**What it does:**
Draws the house shape on the provided canvas. It creates a path for the house outline and door, then draws a portion of this path based on the current progress value.

## **shouldRepaint**
- **Parameters:**
  - `oldDelegate` (CustomPainter): The previous instance of the painter
- **Return type:** bool

**What it does:**
Determines if the painter should repaint. Always returns true to ensure continuous animation.