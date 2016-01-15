# Add String Resources

By default, your Android project includes a string resource file at `res/values/strings.xml`. Here, you'll add a new string named "`edit_message`" and set the value to "Enter a message."

1.	In Android Studio, from the `res/values` directory, open `strings.xml`.

2.	Add a line for a string named "`edit_message`" with the value, "Enter a message".

3.	Add a line for a string named "`button_send`" with the value, "Send".

You'll create the button that uses this string in the next section.

The result for `strings.xml` looks like this:

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <string name="app_name">My First App</string>
    <string name="edit_message">Enter a message</string>
    <string name="button_send">Send</string>
    <string name="action_settings">Settings</string>
</resources>
```

For text in the user interface, always specify each string as a resource. String resources allow you to manage all UI text in a single location, which makes the text easier to find and update. Externalizing the strings also allows you to localize your app to different languages by providing alternative definitions for each string resource.

For more information about using string resources to localize your app for other languages, see the Supporting Different Devices class.