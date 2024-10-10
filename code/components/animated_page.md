---
layout: page
---

# **AnimatedPage**

## **Constructor**
- **Name:** AnimatedPage
- **Parameters:**
  - `key` (Key?): The widget's key
  - `child` (Widget): The widget to be animated
  - `duration` (Duration): The duration of the animation

**What it does:**
AnimatedPage is an abstract class that extends StatelessWidget. It provides a base implementation for creating animated page transitions. The class wraps its child widget in an AnimatedSwitcher, allowing for smooth transitions between different states of the child widget.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
The build method constructs and returns an AnimatedSwitcher widget with the specified duration and child. This allows for animated transitions when the child widget changes.


# **FadeSlideInPage**

## **Constructor**
- **Name:** FadeSlideInPage
- **Parameters:**
  - `key` (Key?): The widget's key
  - `child` (Widget): The widget to be animated

**What it does:**
FadeSlideInPage is a concrete implementation of AnimatedPage that creates a fade and slide-in animation effect for its child widget.

## **build**
- **Parameters:**
  - `context` (BuildContext): The build context
- **Return type:** Widget

**What it does:**
The build method creates a TweenAnimationBuilder that animates the opacity and vertical position of the child widget. It produces a combined fade and slide-in effect, where the child widget fades in while sliding up from a slightly lower position.