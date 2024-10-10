# **TextClick**

## **Constructor**
- **Name:** TextClick
- **Parameters:**
  - `key` (Key?): The widget's key
  - `text` (String): The text to be displayed
  - `tap` (Function): The function to be called when the text is tapped

**What it does:**
TextClick is a StatelessWidget that creates a tappable text element. It wraps the provided text in a RichText widget, allowing for custom styling and tap recognition.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
The build method constructs and returns a RichText widget. This widget contains a single TextSpan with the following properties:
- Displays the provided text
- Applies a grey color to the text
- Attaches a TapGestureRecognizer to make the text tappable
- Executes the provided tap function when the text is tapped

This setup creates an interactive text element that can trigger a specific action when tapped, while maintaining a simple, styled appearance.