# Respond to the Send Button

1.	In Android Studio, from the `res/layout` directory, edit the `content_my.xml` file.

2.	Add the `android:onClick` attribute to the <`Button`> element.

res/layout/content_my.xml

```xml
<Button
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:text="@string/button_send"
    android:onClick="sendMessage" />
```

The `android:onClick` attribute’s value, "`sendMessage`", is the name of a method in your activity that the system calls when the user clicks the button.

3.	In the `java/com.mycompany.myfirstapp` directory, open the `MyActivity.java` file.

4.	Within the `MyActivity` class, add the `sendMessage()` method stub shown below.

java/com.mycompany.myfirstapp/MyActivity.java

```java
/** Called when the user clicks the Send button */
public void sendMessage(View view) {
    // Do something in response to button
}
```

In order for the system to match this method to the method name given to `android:onClick`, the signature must be exactly as shown. Specifically, the method must:

* Be public
* Have a void return value
* Have a `View` as the only parameter (this will be the `View` that was clicked)

Next, you’ll fill in this method to read the contents of the text field and deliver that text to another activity.