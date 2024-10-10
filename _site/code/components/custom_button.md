# **CustomButton**

## **Constructor**
- **Name:** CustomButton
- **Parameters:**
  - `key` (Key?): The widget's key
  - `onTap` (Function()?): The function to be called when the button is tapped
  - `text` (String): The text to display on the button
  - `backgroundColor` (Color?): The background color of the button (default: Colors.black)
  - `textColor` (Color?): The color of the text on the button (default: Colors.white)

**What it does:**
CustomButton is a StatelessWidget that creates a customizable button with configurable text, colors, and tap behavior.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
The build method constructs and returns a GestureDetector wrapped around a Container. This creates a tappable area with customizable appearance. The Container includes padding, margin, background color, and border radius. Inside the Container, it displays centered text with customizable style.

