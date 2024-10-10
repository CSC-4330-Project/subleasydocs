---
layout: page
---

# ComfortableColors Class Documentation

The `ComfortableColors` class defines a set of color constants for use in a Flutter application. These colors create a warm, comfortable color scheme.

## Color Constants

**`background`**
- **Value:** `Color(0xFFF5E6D3)`
- **Description:** A soft beige color intended for use as a background.

**`primary`**
- **Value:** `Color(0xFF7D5A50)`
- **Description:** A warm brown color, likely to be used as the primary color in the app's color scheme.

**`secondary`**
- **Value:** `Color(0xFFB4846C)`
- **Description:** A soft terracotta color, intended as a secondary color in the app's palette.

**`accent`**
- **Value:** `Color(0xFFE5B299)`
- **Description:** A peachy color to be used as an accent in the application.

**`text`**
- **Value:** `Color(0xFF5D4037)`
- **Description:** A dark brown color, intended for text elements in the app.

## Usage

These color constants can be used throughout the application to maintain a consistent color scheme. For example:

```dart
Container(
  color: ComfortableColors.background,
  child: Text(
    'Hello, World!',
    style: TextStyle(color: ComfortableColors.text),
  ),
)
```

This class provides a centralized location for color definitions, making it easier to maintain a consistent look and feel across the application.