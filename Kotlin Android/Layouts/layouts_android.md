# Android UI Layouts
The basic building block for user interface is a **View** object which is created from the View class and occupies a rectangular area on the screen and is responsible for drawing and event handling. View is the base class for widgets, which are used to create interactive UI components like buttons, text fields, etc.

The **ViewGroup** is a subclass of **View** and provides invisible container that hold other Views or other ViewGroups and define their layout properties.

At third level we have different layouts which are subclasses of ViewGroup class and a typical layout defines the visual structure for an Android user interface and can be created either at run time using **View**/**ViewGroup** objects or you can declare your layout using simple XML file main_layout.xml which is located in the res/layout folder of your project.

![](https://www.tutorialspoint.com/android/images/layout.jpg)

<br>

## **Layout Parameters**

This tutorial is more about creating your GUI based on layouts defined in XML file. A layout may contain any type of widgets such as buttons, labels, textboxes, and so on. Following is a simple example of XML file having LinearLayout −
```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
   android:layout_width="fill_parent"
   android:layout_height="fill_parent"
   android:orientation="vertical" >
   
   <TextView android:id="@+id/text"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:text="This is a TextView" />
      
   <Button android:id="@+id/button"
      android:layout_width="wrap_content"
      android:layout_height="wrap_content"
      android:text="This is a Button" />
      
   <!-- More GUI components go here  -->
   
</LinearLayout>
```



Once your layout has created, you can load the layout resource from your application code, in your Activity.onCreate() callback implementation as shown below −
```kotlin
public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   setContentView(R.layout.activity_main);
}
```



## **Types of Android Layout**
- **Android Linear Layout:** LinearLayout is a ViewGroup subclass, used to provide child View elements one by one either in a particular direction either horizontally or vertically based on the orientation property.
<p align ="center">
<img src = https://www.tutorialspoint.com/android/images/liner.jpg height = 313.3 width = 585 >
</p>

- **Android Relative Layout:** RelativeLayout is a ViewGroup subclass, used to specify the position of child View elements relative to each other like (A to the right of B) or relative to the parent (fix to the top of the parent).

- **Android Constraint Layout:** ConstraintLayout is a ViewGroup subclass, used to specify the position of layout constraints for every child View relative to other views present. A ConstraintLayout is similar to a RelativeLayout, but having more power.
<p align ="center">

![](https://websitehcm.com/wp-content/uploads/2021/07/image-866.png)
</p>

- **Android Frame Layout:** FrameLayout is a ViewGroup subclass, used to specify the position of View elements it contains on the top of each other to display only a single View inside the FrameLayout.

- **Android Table Layout:** TableLayout is a ViewGroup subclass, used to display the child View elements in rows and columns.
<p align ="center">

![](https://w7.pngwing.com/pngs/786/698/png-transparent-create-an-app-rows-and-columns-android-table-best-layout-design-angle-text-orange.png)
</p>

- **Android Web View:** WebView is a browser that is used to display the web pages in our activity layout.
<p align ="center">

![](https://i.ytimg.com/vi/ZK-nNMA0bJc/maxresdefault.jpg)
</p>

- **Android ListView:** ListView is a ViewGroup, used to display scrollable lists of items in a single column.
<p align ="center">

![](https://www.tutorialkart.com/wp-content/uploads/2018/04/android-listview-refresh.png)
</p>

- **Android Grid View:** GridView is a ViewGroup that is used to display a scrollable list of items in a grid view of rows and columns.
<p align ="center">
<img src ="https://miro.medium.com/max/1272/1*eUV7bM2sWDU6ruY-wcvNgg.png" height = 512 >
</p>

<br>

## **Create elements in the Kotlin file Dynamically**
We can create or instantiate UI elements or widgets during runtime by using the custom View and ViewGroup objects programmatically in the Kotlin file. Below is the example of creating a layout using LinearLayout to hold an EditText and a Button in an activity programmatically. 

```kotlin
import android.os.Bundle
import android.widget.Button
import android.widget.EditText
import android.widget.LinearLayout
import android.widget.Toast
import android.appcompat.app.AppCompatActivity

class MainActivity : AppCompatActivity() {

	override fun onCreate(savedInstanceState: Bundle?) {
		super.onCreate(savedInstanceState)
		setContentView(R.layout.activity_main)

		// create the button
		val showButton = Button(this)
		showButton.setText("Submit")

		// create the editText
		val editText = EditText(this)

		val linearLayout = findViewById<LinearLayout>(R.id.l_layout)
		linearLayout.addView(editText)
		linearLayout.addView(showButton)

		// Setting On Click Listener
		showButton.setOnClickListener
		{
			// Getting the user input
			val text = editText.text

			// Showing the user input
			Toast.makeText(this, text, Toast.LENGTH_SHORT).show()
		}
	}
}

```
<br>

## **Different Attributes of Layouts**

XML attributes | Description 
 ------------ | ------------- 
android:id	| Used to specify the id of the view.
android:layout_width | Used to declare the width of View and ViewGroup elements in the layout.
android:layout_height |	Used to declare the height of View and ViewGroup elements in the layout.
android:layout_marginLeft |	Used to declare the extra space used on the left side of View and ViewGroup elements.
android:layout_marginRight | Used to declare the extra space used on the right side of View and ViewGroup elements.
android:layout_marginTop | Used to declare the extra space used in the top side of View and ViewGroup elements.
android:layout_marginBottom | Used to declare the extra space used in the bottom side of View and ViewGroup elements.
android:layout_gravity | Used to define how child Views are positioned in the layout.

<br>

### Resources
[Google UI Guide](https://developer.android.com/develop/ui/views/layout/declaring-layout)