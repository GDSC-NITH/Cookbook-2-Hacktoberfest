# App Bar
## **About AppBar Widget**

[Click here to check in official docs of Flutter](https://api.flutter.dev/flutter/material/AppBar-class.html)

AppBar is usually the topmost component of the app (or sometimes the bottom-most), it contains the toolbar and some other common action buttons. As all the components in a flutter application are a widget or a combination of widgets. So AppBar is also a built-in class or widget in flutter which gives the functionality of the AppBar out of the box. The AppBar widget is based on Material Design and much of the information is already provided by other classes like MediaQuery, Scaffold as to where the content of the AppBar should be placed. Though the AppBar class is very flexible and can be easily customized, we can also use the *SilverAppBar* widget which gives scrollable functionality to the app bar. Or we can create our own custom app bar from scratch.

<br>

***
<br>

## **AppBar Widget Constructor**
<br>

```Dart
AppBar(
   {Key? key,
   Widget? leading,
   bool automaticallyImplyLeading: true,
   Widget? title,
   List? actions,
   Widget? flexibleSpace,
   PreferredSizeWidget? bottom,
   double? elevation,
   Color? shadowColor,
   ShapeBorder? shape,
   Color? backgroundColor,
   Color? foregroundColor,
   Brightness? brightness,
   IconThemeData? iconTheme,
   IconThemeData? actionsIconTheme,
   TextTheme? textTheme,
   bool primary: true,
   bool? centerTitle,
   bool excludeHeaderSemantics: false,
   double? titleSpacing,
   double toolbarOpacity: 1.0,
   double bottomOpacity: 1.0,
   double? toolbarHeight,
   double? leadingWidth,
   bool? backwardsCompatibility,
   TextStyle? toolbarTextStyle,
   TextStyle? titleTextStyle,
   SystemUiOverlayStyle? systemOverlayStyle}
)
```
package:flutter/src/material/scaffold.dart

<br>

***
<br>

## **Essential Properties of Scaffold Widget** 

<br>

1. **leading:** You need to pass the widget into this parameter and it will be placed on the start-left side of an appbar. If there is any drawer into the same scaffold where app bar is implemented, the menu icon will automatically appear. The back button will appear in the same way when there is a back routing history of your app. 

```Dart
AppBar( //appbar widget on Scaffold
  leading: IconButton( //menu icon button at start left of appbar
    onPressed: (){
         //code to execute when this button is pressed
    },
    icon: Icon(Icons.menu),
  ),
),
```
**Output**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/e8c0653fea13f91bf3c48159f7c24f78.webp" alt="appBar Output">
</p>

2. **automaticallyImplyLeading:** If you have implemented a drawer to the same scaffold where you have placed appBar, there will be a menu icon placed at **leading** of app bar automatically. In the same way, whenever there is backward routing history, the back icon will appear at leading. You can control this behavior of appBar with **automaticallyImplyLeading** property. By default, its value is **true**.  Make it false, if you don't want automatic placement of menu or back icons at leading. 

```Dart
AppBar(
  automaticallyImplyLeading: false,
)
```

3. **title:** This widget displays after the leading widget from the left side of app bar. Normally, it is used to show the title of the active screen of the app. You can pass any widget into it, normally, Text() widget is passed to show textual title on app bar. 

```Dart
AppBar(
  title:Text("Title of App"),
)
```

**Output**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/ff4d5fbbafdf976cfdc032e3bde78de5.webp" alt="title appBar Output">
</p>

4. **actions:** You need to pass the list of widget into this parameter of AppBar class. The widgets will be displayed at the right side of app bar. Normally, quick action buttons are placed on this property. 

```Dart
AppBar(
  actions: [
    IconButton(
      icon: Icon(Icons.camera), 
      onPressed: (){
        //code to execute when this button is pressed
      }
    ),

    IconButton(
      icon: Icon(Icons.search), 
      onPressed: (){
        //code to execute when this button is pressed
      }
    ),

    //more widgets to place here
  ],
)
```

**Output**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/2d6cc4b2d139a53512fb8cbb3086ae2e.webp" alt="actions appBar Output">
</p>

5. **bottom:** You need to pass a widget with constant height into this property. You can implement *CupertinoTabBar, ObstructingPreferredSizeWidget, PreferredSize, TabBar* into this property. 

```Dart
DefaultTabController(
  length: 2, //numbers of tab
  child:Scaffold(
    appBar: AppBar( //appbar widget on Scaffold
      bottom: TabBar(
        tabs: [
            Tab(icon: Icon(Icons.home)),
            Tab(icon: Icon(Icons.send))
            //more tabs here
        ],
      ),
    ), 
  )   
)
```

**Output:**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/389bc7bb1e1c2a5e7e147703232a88f6.webp" alt="bottom appBar Output">
</p>


6. **elevation:** This property is used to raise the app bar using shadow, you need to pass the double value which determines the height of elevation of app bar.

```Dart
AppBar(
  elevation: 30.0,
)
```

**Output:**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/e2230b853516e7b05d79744fbd4c9c13.webp" alt="elevation appBar Output">
</p>

7. **backgroundColor:** This property is used to set the background color of app bar.

```Dart
AppBar(
  backgroundColor: Colors.redAccent,
)
```

**Output:**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/10a7cdd970fe135cf4f7bb55c0e3b59f.webp" alt="background appBar Output">
</p>

8. **brightness:** This property is used to set the brightness scheme of app bar. Suppose, you have set background color to dark type color then you need to set the brightness to dark so that the content inside it gets displayed in a light color or vice versa. 

```Dart
AppBar(
  brightness: Brightness.dark,
)
```

**Output:**

Dark icon on status bar due to **Brightness.light**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/087408522c31eeb1f982bc0eaf81d35f.webp" alt="appBar Output">
</p>

Light icon on status bar due to **Brightness.dark**

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/05/a760880003e7ddedfef56acb3b09697f.webp" alt="appBar Output">
</p>

9. **shape:** This property is used to give shape to the Appbar and manage its shadow.

<br>

***
<br>

## **SAMPLE**

<br>

### **Code**

In this example, we are going to see a Scaffold widget with an AppBar, BottomAppBar, FloatingActionButton, floatingActionButtonLocation, and drawer properties.

```Dart
import 'package:flutter/material.dart';

void main() {
   runApp(MyApp()); 
}

class MyApp extends StatelessWidget{
  @override
  Widget build(BuildContext context) {
    return DefaultTabController( //controller for TabBar
      length: 2, //lenght of tabs in TabBar
      child: MaterialApp(
         home: HomePage(),
      )
    );
  }
}

class HomePage extends StatelessWidget{
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.blue[100],
      appBar: AppBar(
          title:Text("Title of App"), //title of app
          backgroundColor: Colors.redAccent, //background color of app bar
          brightness: Brightness.dark, //redAccent is darker color so set brightness to dark
          elevation: 5.0, //elevation value of appbar
           bottom: TabBar( //tabbar at bottom of appbar
            onTap: (index){
              print("selected tab is $index");
            },
            tabs: [
                Tab(icon: Icon(Icons.home)),
                Tab(icon: Icon(Icons.send))
                //more tabs here
            ],
          ),
          actions: [ //actions widget in appbar
            IconButton(
              icon: Icon(Icons.camera), 
              onPressed: (){
                //code to execute when this button is pressed
              }
            ),

            IconButton(
              icon: Icon(Icons.search), 
              onPressed: (){
                //code to execute when this button is pressed
              }
            ),
            //more widgets to place here
          ], 
        ),

        drawer: Drawer(), //drawer on scaffold, it will create menu icon on appbar
 
        body: Center( //content body on scaffold
           child: Text("AppBar example")
        )
     );
  }
}  
```
<br>

### **Output**
***
<br>

AppBar with title and redAccent background color

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/03/3ef815416f775098fe977004015c6193.webp">
</p>

AppBar with bottom TabBar and actions

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/03/93db85ed909c13838ff95ccfa94cebd9.webp">
</p>

AppBar with automatic leading due to Drawer in scaffold

<p align="center">
  <img src="https://www.fluttercampus.com/img/uploads/web/2021/03/c7e1249ffc03eb9ded908c236bd1996d.webp">
</p>

<br>

***
<br>

## **Resources:**
<br>

* [**Flutter Campus**](https://www.fluttercampus.com/tutorial/10/flutter-appbar/)
* [**GFG**](https://www.geeksforgeeks.org/flutter-appbar-widget/)