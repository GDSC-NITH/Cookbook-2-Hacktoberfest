# **Basic Layouts in Jetpack Compose**
<br>

### Jetpack Compose is the modern UI-tooling from Google. It’s first stable release was in July 2021 and so far, many Kotlin developers are loving this new way of designing the UI in Android. Let’s take a look at some features of Jetpack Compose and how it differs from traditional XML.

> *In my opinion, Jetpack Compose is the future of Android UI development and we must adopt fastly.*

<br>

## **What is Jetpack Compose ?**

![](https://miro.medium.com/max/715/1*fChLMnM4VlmXGqaAqvjgdA.png)

### Jetpack Compose is a modern toolkit that allows us to build our screens in a declarative approach writing less code. Android UI Development is now more powerful and more decoupled.

### Before Jetpack Compose, we were using XML layouts to build the native UI. We had a very dependent structure when we build the screens with XML. Also, fragments are very heavy components for the UI. Jetpack Compose allows us to build the same UI with a declarative UI approach and with less code.

<br>

## **Why should we use Jetpack Compose ?**

### In my opinion, it’s more than easy from XML and Kotlin
### If we look technically:

- Declarative UI is cleaner, readable, and performant than Imperative UI.
- Compose allows you to do more with less code compared to XML.
- Compose is Intuitive. This means that you just need to tell Compose what you want to show the user.
- Compose is compatible with all your existing code: you can call Compose code from Views and Views from Compose. Also integrated with many Jetpack Libraries.
- Compose improves your build time and APK size.

<br>

## **The Difference**
### 1. **State Management**
### “State in an app is any value that can change over time.”- Google
### Compose is declarative so the only way to update it is by calling with different arguments.

### Initial Composition: creation of a Composition by running composables the first time.

### Recomposition: Re-running composables to update the Composition when data (state) changes.
### Store a data with remember:

```kotlin
val data by remember { mutableStateOf(INITIAL_VALUE) } 
``` 

<br>

### 2. **Animations**
### You cannot have a topic regarding Jetpack Compose and not introduce animations. Animations has been the best feature of Jetpack Compose. XML was not built to create complex animations but Jetpack Compose brings it to the table with a great interface.

### There are tons of different ways you can animate properties and composables. You can trigger the visibility with different enter/exit effects with ```AnimatedVisibility```, creating transitions between elements, and most of all using the ```animate*AsState```, where * represents a data type like Int or Float.

!["Animations of Jetpack Compose"](https://cdn-images-1.medium.com/fit/t/1600/480/1*Y_Oyl3QcIdlzDVkeKsZgBA.gif)

### Jetpack Compose provides you a variety of the different configurations that you can use to customize the animation you would want in your screen.

<br>

### 3. **Basic UI Components**
### Now let’s build the same view using Xml and Jetpack Compose and look at the differences on the code side.
### Here is the target view structure:

![](https://miro.medium.com/max/640/1*790lNRXn5cGtHVjgHLI5Ew.png)

### **Build With XML**

```xml
<?xml version="1.0" encoding="utf-8"?>
<ScrollView xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center"
        android:orientation="vertical">

        <TextView
            android:id="@+id/txtHeader"
            style="@style/TextAppearance.MaterialComponents.Headline2"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginBottom="20dp"
            android:paddingHorizontal="20dp"
            android:text="Hello Compose"
            android:textAlignment="center" />

        <ImageView
            android:id="@+id/imgSelectedAnimal"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:contentDescription="selected animal image"
            android:paddingHorizontal="20dp"
            android:scaleType="centerCrop"
            android:layout_marginBottom="20dp"
            android:src="@drawable/ic_launcher_foreground" />

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_marginBottom="20dp"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:orientation="horizontal">

            <RadioButton
                android:id="@+id/radioButtonDog"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content" />

            <Space
                android:layout_width="100dp"
                android:layout_height="wrap_content" />

            <RadioButton
                android:id="@+id/radioButtonCat"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content" />

        </LinearLayout>

        <Button
            android:id="@+id/btnScrollToTop"
            android:layout_width="wrap_content"
            android:backgroundTint="@color/black"
            android:textColor="@color/white"
            android:text="Scroll to Top"
            android:textAllCaps="false"
            android:layout_height="wrap_content"/>

    </LinearLayout>

</ScrollView>
```

<br>

### **Build with Jetpack Compose**

```kotlin
        val scrollState = rememberScrollState()
        val scope = rememberCoroutineScope()
        var selectedAnimal by remember { mutableStateOf<Animal?>(null) }

        Column(
            modifier = Modifier
                .fillMaxSize()
                .verticalScroll(scrollState),
            verticalArrangement = Arrangement.spacedBy(20.dp),
            horizontalAlignment = Alignment.CenterHorizontally
        ) {
            Text(
                text = "Hello Compose",
                style = MaterialTheme.typography.h2,
                textAlign = TextAlign.Center,
                modifier = Modifier
                    .fillMaxWidth()
                    .padding(horizontal = 24.dp)
            )

            Image(
                painter = painterResource(
                    id = selectedAnimal?.imageSrc ?: R.drawable.ic_launcher_foreground
                ),
                contentDescription = "selected animal image",
                modifier = Modifier
                    .fillMaxWidth(fraction = 0.75f)
                    .aspectRatio(3 / 8f),
                contentScale = ContentScale.Crop
            )

            Row(
                modifier = Modifier
                    .fillMaxWidth()
                    .wrapContentHeight(),
                horizontalArrangement = Arrangement.SpaceEvenly
            ) {

                RadioButton(
                    selected = selectedAnimal is Animal.Dog,
                    onClick = { selectedAnimal = Animal.Dog },
                )

                RadioButton(
                    selected = selectedAnimal is Animal.Cat,
                    onClick = { selectedAnimal = Animal.Cat },
                )
            }

            Button(
                onClick = {
                    scope.launch {
                        scrollState.animateScrollTo(0)
                    }
                },
                colors = ButtonDefaults.buttonColors(
                    backgroundColor = Color.Black,
                    contentColor = Color.White,
                )
            ) {
                Text(text = "Scroll to Top")
            }

            Spacer(modifier = Modifier.size(100.dp))
        }
```

<br>

## **Conclusion**
### No, with the introduction of Jetpack Compose, it doesn’t mean that XML is deprecated. Google took them three years to officially declare Kotlin as their language and introduced a UI tooling kit that can run just in Kotlin. Similarly, within a few years, Compose will be the preferred way of dealing with UI and Google will create new components which is possible to render only if you use Jetpack Compose.
### To me, Jetpack Compose is a revolution of Android UI development. Less code and more understandable code, declarative UI approach, managing state, and more. In addition, it can work directly with the jetpack libraries.

<br>
<br>

## Official Articles

[Why adopt Jetpack Compose](https://developer.android.com/jetpack/compose/why-adopt)

[Ergonomics of Jetpack Compose](https://developer.android.com/jetpack/compose/ergonomics)