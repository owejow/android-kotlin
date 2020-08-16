# 05 Debugging Android Apps

## Exceptions and Stacktraces

- Look for last exception in logcat
- click on link to source code referenced by logcat
- if crash occurs on a device that is not plugged in, it will store
    the last lines written to the log. This data is usually stored on 
    the device for around 10 minutes (depends on device). 


```kotlin

// logging debug message
private fun updateQuestion() {
    Log.d(TAG, "Updating question text", Exception())
    val questionTextResId = quizViewModel.currentQuestionText
    questionTextView.setText(questionTextResId)
}
```

*Attach Debugger to Android Process*: attach the debugger to a running application. 

## Android Lint: 

*Android Lint* is a static analyzer for Android code

Manually run lint: Select *Analyze* -> *Inspect Code* from Menu bar.

## Issues with the R class

If see build errors persist or appear seemingly out of nowhere: 

- Recheck the validity of XML in your resource files. 
- Layout XML is not always validated. 
- Clean your project. Select *Build* -> *Clean* Project. 
- Sync your project with Gradle.
- Run Android Lint. 
