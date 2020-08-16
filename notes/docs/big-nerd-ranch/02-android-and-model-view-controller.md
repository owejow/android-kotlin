# Android and Model-View-Controller

- Use data keyword to indicate class will hold data:

```java

// compiler will automatically define methods like equals, hasCode, toString
// for data class
data class Question(@StringRes val textResId: Int, val answer: Boolean) {

}

```

## Model-View-Controller

- Model holds and manages the data
- View layer contain view objects
- Controller tie view and model objects. It contains application logic. Typically
    a subclass of activity or fragment.

Once the controller gets too complicated consider using: Model-View-View Model pattern

## Adding an Icon

Icons can be added to <AppName>/app/src/main/res/

Switch the project to Android view to see drawable files

- Anything added to res/drawable will be automatically assigned a resource id

!!! Note
    Filenames must be lowercase and contain no spaces

- The resouce ID are not qualified by screen density. The OS will automatically
    determine screen density at runtime.


```xml
<Button
    android:id="@+id/next_button"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/next_button"
    android:drawableEnd="@drawable/arrow_right"  // how reference drawable
    android:drawablePadding="4dp"/>          
```

## Screen Pixel Densities

Android automcatically scales images to different pixel densities using density 
qualified drawable folders (e.g. drawable-xhdpi).


There are different ways to specify dimension units on the screen:

- *px*: stands for pixel or one onscreen pixel. Pixels do not scale relative
    to display density. Their use is not recommended.

- *dp*: density-independent pixel (usually pronounced dip). Use this value for margins
    or padding, or anything else for which you would specify using a pixel value. A
    *dp* is always 1/160th of an inch on the device's screen. When display is higher 
    density, the *dp* will expand to fill a larger number of screen pixels.

- *sp*: scale-independent pixel. They are scale-independent pixels that take into account the user's font size preference. You should almost always use *sp* to set display 
 text size.

- *pt*, *mm*, *in*: scaled units like *dp* that allow you to specify interface
    sizes in points (1/72nd of an inch), milimeters, or inches. Not recommended 
    to use these units. Not all devices are correctly configured to use these units. 

!!! Note
    Recommended to use dp and sp. These units are translated to pixels at runtime.
