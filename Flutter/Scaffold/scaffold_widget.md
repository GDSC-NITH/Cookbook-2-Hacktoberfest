# Scaffold
## **About Scaffold Widget**

[Click here to check in official docs of Flutter](https://api.flutter.dev/flutter/material/Scaffold-class.html)

The Scaffold is a widget in Flutter used to implements the basic material **design visual layout structure**. It is quick enough to create a general-purpose mobile application and contains almost everything we need to create a **functional** and **responsive** Flutter apps.

The Scaffold class is a shortcut to set up the look and design of our app that allows us not to build the individual visual elements manually. It saves our time to write more code for the look and feel of the app. Scaffold is a class in flutter which provides many widgets or we can say APIs like Drawer, SnackBar, BottomNavigationBar, FloatingActionButton, AppBar, etc. **Scaffold will expand or occupy the whole device screen**. It will occupy the available space. Scaffold will provide a framework to implement the basic material design layout of the application. The following are the constructor and properties of the Scaffold widget class.

<br>

***
<br>

## **Text Widget Constructor**
<br>

```Dart
const Scaffold({
    Key key,
    this.appBar,
    this.body,
    this.floatingActionButton,
    this.floatingActionButtonLocation,
    this.floatingActionButtonAnimator,
    this.persistentFooterButtons,
    this.drawer,
    this.endDrawer,
    this.bottomNavigationBar,
    this.bottomSheet,
    this.backgroundColor,
    this.resizeToAvoidBottomPadding,
    this.resizeToAvoidBottomInset,
    this.primary = true,
    this.drawerDragStartBehavior = DragStartBehavior.start,
    this.extendBody = false,
    this.drawerScrimColor,
})
```
package:flutter/src/material/scaffold.dart

<br>

***
<br>

## **Essential Properties of Scaffold Widget** 

<br>

1. **appBar:** It displays a horizontal bar which mainly placed at the top of the Scaffold. appBar uses the widget AppBar which has its own properties like elevation, title, brightness, etc.

```Dart
Widget build(BuildContext context)
{
  return Scaffold(
    appBar: AppBar(
      title: const Text('GeeksforGeeks'),
    ),
```
**Output**

<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20191225231624/Screenshot_1576607980-169x300.png" alt="appBar Scaffold Output" width="250" height="520">
</p>

2. **body:** t will display the main or primary content in the Scaffold. It is below the appBar and under the floatingActionButton. The widgets inside the body are at the left-corner by default. 

```Dart
Widget build(BuildContext context) {
   return Scaffold(
     appBar: AppBar(title: const Text('GeeksforGeeks')),
     body: const Center(
       child: Text(
         "Welcome to GeeksforGeeks!!!",
         style: TextStyle(
           color: Colors.black,
           fontSize: 40.0,
         ),
       ),
     ),
   );
 }
```
In this example, we have displayed the text Welcome to GeeksforGeeks!!! in the body. We have displayed the text in the center of the page using Center widget. For styling the text, we have used *TextStyle* widget. 

**Output**

<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20191225232615/body-example-169x300.png" alt="body Scaffold Output" width="250" height="520">
</p>

3. **floatingActionButton:** FloatingActionButton is a button that is placed at the right bottom corner by default. FloatingActionButton is an icon button that floats over the content of the screen at a fixed place. If we scroll the page its position won’t change, it will be fixed.available space.

```Dart
Widget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(title: const Text('GeeksforGeeks')),
    body: const Center(
      child: Text(
        "Welcome to GeeksforGeeks!!!",
        style: TextStyle(
          color: Colors.black,
          fontSize: 40.0,
        ),
      ),
    ),
    floatingActionButton: FloatingActionButton(
      elevation: 10.0,
      child: const Icon(Icons.add),
      onPressed: () {
        // action on button press
      },
    ),
  );
}
```

Here the elevation property is used to give a shadow effect to the button. Icon is used to put the icon of the button using some preloaded icons in flutter SDK. The *onPressed()* is a function that will be called when the button is pressed and the statements inside the function will be executed. 

**Output**

<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20191225233726/floatingActionButton-Example-169x300.png" alt="floatingActionButton Scaffold Output" width="250" height="520">
</p>

4. **drawer:** drawer is a slider menu or a panel which is displayed at the side of the Scaffold. The user has to swipe left to right or right to left according to the action defined to access the drawer menu. In the Appbar, an appropriate icon for the drawer is set automatically at a particular position. The gesture to open the drawer is also set automatically. It is handled by the Scaffold. 

```Dart
drawer: Drawer(
  child: ListView(
    children: const <Widget>[
      DrawerHeader(
        decoration: BoxDecoration(
          color: Colors.green,
        ),
        child: Text(
          'GeeksforGeeks',
          style: TextStyle(
            color: Colors.green,
            fontSize: 24,
          ),
        ),
      ),
      ListTile(
        title: Text('Item 1'),
      ),
      ListTile(
        title: Text('Item 2'),
      ),
    ],
  ),
),
```

As a parent widget we took ListView and inside it, we divided the panel into two parts, Header and Menu.DrawerHeader is used to modify the header of the panel. In header we can display icon or details of user according to the application. We have used ListTile to add the items to the menu. 

**Output**

<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20191225235024/drawer-example-169x300.png" alt="drawer Scaffold Output" width="250" height="520">
</p>

5. **bottomNavigationBar:** bottomNavigationBar is like a menu at the bottom of the Scaffold. We have seen this navigationbar in most of the applications. We can add multiple icons or texts or both in the bar as items. 

```Dart
bottomNavigationBar: BottomNavigationBar(
        currentIndex: 0,
        fixedColor: Colors.green,
        items: const [
          BottomNavigationBarItem(
            label: "Home",
            icon: Icon(Icons.home),
          ),
          BottomNavigationBarItem(
            label: "Search",
            icon: Icon(Icons.search),
          ),
          BottomNavigationBarItem(
            label: "Profile",
            icon: Icon(Icons.account_circle),
          ),
        ],
        onTap: (int indexOfItem) {}),
```

We use BottomNavigationBar widget to display the bar. For the color of active icon, we use the fixedColor property. To add items in the bar we use BottomNavigationBarItems widget, inside which we give text and icon. For the action performed on the tapping on the items, we have onTap(int indexOfItem) function which works according to the index position of the item. 

**Output:**

<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/20191227001057/bottomNavigationBar-169x300.png" alt="bottomNavigationBar Scaffold Output" width="250" height="520">
</p>


6. **backgroundColor:** used to set the color of the whole Scaffold widget.

7. **floatingActionButtonAnimator:** used to provide animation to move floatingActionButton.

8. **primary:** to tell whether the Scaffold will be displayed or not.

9. **drawerScrimColor:** used to define the color for the primary content while a drawer is open.

10. **bottomSheet:** This property takes in a widget  (final) as the object to display it at the bottom of the screen.

11. **drawerDragStartBehaviour:** This property holds DragStartBehavior enum as the object to determine the drag behaviour of the drawer.

12. **drawerEdgeDragWidth:** This determines the area under which a swipe or a drag will result in the opening of the drawer. And it takes in a double as the object.

13. **drawerEnableOpenGesture:** This property holds in a boolean value as the object to determine the drag gesture will open the drawer or not, by default it is set to true.

14. **endDrawer:** The endDrawer property takes in a widget as the parameter. It is similar to the Drawer, except the fact it opens in the opposite direction.

15. **endDrawerEnableOpenGesture:** Again this property takes in a boolean value as the object to determine whether the drag gesture will open the endDrawer or not.

16. **extendBody:** The extendBody property takes in a boolean as the object. By default, this property is always false but it must not be null. If it is set to true in the presence of a bottomNavigationBar or persistentFooterButtons, then the height of these is added to the body and they are shifted beneath the body.

17. **extendBodyBehindAppBar:**  This property also takes in a boolean as the object. By default, this property is always false but it must not be null. If it is set to true the appBar instead of being on the body is extended above it and its height is added to the body. This property is used when the color of the appBar is not fully opaque.

18. **floatingActionButtonLocation:** This property is responsible for the location of the floatingActionBotton.

19. **persistentFooterButton:** This property takes in a list of widgets. Which are usually buttons that are displayed underneath the scaffold.

20. **resizeToAvoidBottomInsets:** This property takes in a boolean value as the object. If set to true then the floating widgets on the scaffold resize themselves to avoid getting in the way of the on-screen keyboard.

<br>

***
<br>

## **SAMPLE**

<br>

### **Code**

In this example, we are going to see a Scaffold widget with an AppBar, BottomAppBar, FloatingActionButton, floatingActionButtonLocation, and drawer properties.

```Dart
import 'package:flutter/material.dart';  
  
void main() => runApp(MyApp());  
  
/// This Widget is the main application widget.  
class MyApp extends StatelessWidget {  
  @override  
  Widget build(BuildContext context) {  
    return MaterialApp(  
      home: MyStatefulWidget(),  
    );  
  }  
}  
  
class MyStatefulWidget extends StatefulWidget {  
  MyStatefulWidget({Key key}) : super(key: key);  
  
  @override  
  _MyStatefulWidgetState createState() => _MyStatefulWidgetState();  
}  
  
class _MyStatefulWidgetState extends State<MyStatefulWidget> {  
  int _count = 0;  
  
  Widget build(BuildContext context) {  
    return Scaffold(  
      appBar: AppBar(  
        title: Text('Flutter Scaffold Example'),  
      ),  
      body: Center(  
        child: Text('We have pressed the button $_count times.'),  
      ),  
      bottomNavigationBar: BottomAppBar(  
        shape: const CircularNotchedRectangle(),  
        child: Container(  
          height: 50.0,  
        ),  
      ),  
      floatingActionButton: FloatingActionButton(  
        onPressed: () => setState(() {  
          _count++;  
        }),  
        tooltip: 'Increment Counter',  
        child: Icon(Icons.add),  
      ),  
      floatingActionButtonLocation: FloatingActionButtonLocation.endDocked,  
      drawer: Drawer(  
        elevation: 20.0,  
        child: Column(  
          children: <Widget>[  
            UserAccountsDrawerHeader(  
              accountName: Text("javatpoint"),  
              accountEmail: Text("javatpoint@gmail.com"),  
              currentAccountPicture: CircleAvatar(  
                backgroundColor: Colors.yellow,  
                child: Text("abc"),  
              ),  
            ),  
            ListTile(  
              title: new Text("Inbox"),  
              leading: new Icon(Icons.mail),  
            ),  
            Divider( height: 0.1,),  
            ListTile(  
              title: new Text("Primary"),  
              leading: new Icon(Icons.inbox),  
            ),  
            ListTile(  
              title: new Text("Social"),  
              leading: new Icon(Icons.people),  
            ),  
            ListTile(  
              title: new Text("Promotions"),  
              leading: new Icon(Icons.local_offer),  
            )  
          ],  
        ),  
      ),  
    );  
  }  
}  
```
<br>

### **Output**
***
<br>

<p align="center">
  <img src="https://static.javatpoint.com/tutorial/flutter/images/flutter-scaffold.png" width="250" height="520">
</p>

If we click on the three lines that can be seen in the top left corner of the screen, we will see the drawer. The drawer can be swiped right to left or left to right. See the below image.

<p align="center">
  <img src="https://static.javatpoint.com/tutorial/flutter/images/flutter-scaffold2.png" width="250" height="520">
</p>

<br>

***
<br>

## **Resources:**
<br>

* [**JAVAPOINT**](https://www.javatpoint.com/flutter-scaffold)
* [**GFG**](https://www.geeksforgeeks.org/scaffold-class-in-flutter-with-examples/)