[3\. Create the starter Flutter app](#2)
----------------------------------------

Create a simple, templated Flutter app. Create a Flutter project called **hello\_world** as follows.

    $ flutter create hello\_world

    $ cd hello\_world

You'll mostly edit **`lib/main.dart`**, where the Dart code lives.

Replace the contents of **`lib/main.dart`**. Delete all the code from **`lib/main.dart`** and replace it with the following code, which displays "Hello World" in the center of the screen.

    import 'package:flutter/material.dart';

    void main() {
    runApp(const MyApp());
    }

    class MyApp extends StatelessWidget {
    const MyApp({super.key});

    @override
    Widget build(BuildContext context) {
        return MaterialApp(
        title: 'Welcome to Flutter',
        home: Scaffold(
            appBar: AppBar(
            title: const Text('Welcome to Flutter'),
            ),
            body: const Center(
            child: Text('Hello World'),
            ),
        ),
        );
    }
    }

**Tip**: When pasting code into your app, indentation can become skewed. You can fix it with the following Flutter tools:

*   Android Studio/IntelliJ IDEA: Right-click the Dart code and select **Reformat Code with dartfmt**.
*   Visual Studio Code: Right-click and select **Format Document**.
*   Terminal: Run `flutter format <filename>`.

You should see either Android, iOS, Windows, Linux, macOS, or web output, depending on your device.

Windows
![](https://codelabs.developers.google.com/static/codelabs/first-flutter-app-pt1/img/5bfca6716bba2af1.png)
iOS
![](https://codelabs.developers.google.com/static/codelabs/first-flutter-app-pt1/img/2e973d40d6e82114.png)



**Tip**: The first time that you run on a physical device, it can take a while to load. Afterward, you can use hot reload for quick updates. In supported IDEs, **Save** also performs a hot reload if the app is running. When running an app directly from the console using `flutter run`, enter `r` to perform hot reload.

**Observations**

*   This example creates a Material app. [Material](https://material.io/guidelines/) is a visual-design language that's standard on mobile and the web. Flutter offers a rich set of Material widgets.
*   The app extends `StatelessWidget`, which makes the app itself a widget. In Flutter, almost everything is a widget, including alignment, padding, and layout.
*   The `Scaffold` widget, from the Material library, provides a default app bar, a title, and a body property that holds the widget tree for the home screen. The widget subtree can be quite complex.
*   A widget's main job is to provide a `build` method that describes how to display the widget in terms of other, lower-level widgets.
*   The body for this example consists of a `Center` widget containing a `Text` child widget. The `Center` widget aligns its widget subtree to the center of the screen.