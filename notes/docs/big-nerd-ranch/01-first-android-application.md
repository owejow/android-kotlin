# Your First Android App

## App Basics

- Activity is used to manage interactions. All activities are instances of Activity.
- layout defines set of UI objects and its postions


AndroidX artifacts replaces the single support library with many independent libraries.

The layout files should be "snake_case". The activity classes should be PascalCase.

ViewGroup is a View that arranges other views. 

- String resources are added to "res/values/strings.xml". The are used using the construct: "@string/false_button"


!!! Note
    Resource id can be found in build/generated/.../R.java file 


To create a reference for your view object you need to use the "@+" syntax:

```xml
    <Button 
        android:id="@+id/false_button"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/false_button" />
```

## Wiring Up the Widgets

```kotlin
class MainActivity : AppCompatActivity() {

    private lateinit var trueButton: Button  // lateint a non-null value will be provided later
    private lateinit var falseButton: Button
    
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContentView(R.layout.activity_main)
        
        trueButton = findViewById(R.id.true_button)  // referencing inflated widget
        falseButton = findViewById(R.id.false_button)
    }
}
```

## Listener

**SAM** Single abstract method: java interface with a single abstract method.

Kotlin allows the use of lambda syntax to write SAM. 


```kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    trueButton.setOnClickListener { view: View ->  // can remove view: View -> if no arguments
    // Do something in response to the click here
    }

falseButton.setOnClickListener { view: View ->
    // Do something in response to the click here
    }
}
```

## build System

Android uses Gradle as a build system. Command line invocation:

```bash
./gradlew tasks
```  


