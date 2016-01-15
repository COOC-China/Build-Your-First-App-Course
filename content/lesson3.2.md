# Add a Text Field

As with every `View` object, you must define certain XML attributes to specify the `EditText` object's properties.

1.	In the `content_my.xml` file, within the `<LinearLayout>` element, define an `<EditText> `element with the id attribute set to `@+id/edit_message`.

2.	Define the `layout_width` and `layout_height` attributes as `wrap_content`.

3.	Define a `hint` attribute as a string object named `edit_message`.

The `<EditText>` element should read as follows:
```xml
<EditText android:id="@+id/edit_message"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    android:hint="@string/edit_message" />
```
Here are the `<EditText>` attributes you added:

`android:id`


This provides a unique identifier for the view, which you can use to reference the object from your app code, such as to read and manipulate the object (you'll see this in the next lesson).

The at sign (`@`) is required when you're referring to any resource object from XML. It is followed by the resource type (`id` in this case), a slash, then the resource name (`edit_message`).

The plus sign (`+`) before the resource type is needed only when you're defining a resource ID for the first time. When you compile the app, the SDK tools use the ID name to create a new resource ID in your project's `gen/R.java` file that refers to the `EditText` element. With the resource ID declared once this way, other references to the ID do not need the plus sign. Using the plus sign is necessary only when specifying a new resource ID and not needed for concrete resources such as strings or layouts. See the sidebox for more information about resource objects.

`android:layout_width` and `android:layout_height`


Instead of using specific sizes for the width and height, the `"wrap_content"` value specifies that the view should be only as big as needed to fit the contents of the view. If you were to instead use `"match_parent"`, then the `EditText` element would fill the screen, because it would match the size of the parent `LinearLayout`. For more information, see the `Layouts` guide.

`android:hint`


This is a default string to display when the text field is empty. Instead of using a hard-coded string as the value, the `"@string/edit_message"` value refers to a string resource defined in a separate file. Because this refers to a concrete resource (not just an identifier), it does not need the plus sign. However, because you haven't defined the string resource yet, you’ll see a compiler error at first. You'll fix this in the next section by defining the string.

>**Note**: This string resource has the same name as the element ID: `edit_message`. However, references to resources are always scoped by the resource type (such as `id` or `string`), so using the same name does not cause collisions.