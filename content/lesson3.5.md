# Make the Input Box Fill in the Screen Width

To fill the remaining space in your layout with the `EditText` element, do the following:

1.	In the `content_my.xml` file, assign the <`EditText`> element's `layout_weight` attribute a value of 1.

2.	Also, assign <`EditText`> element's `layout_width` attribute a value of `0dp`.

```xml
<EditText
    android:layout_weight="1"
    android:layout_width="0dp"
    ... />
```

To improve the layout efficiency when you specify the weight, you should change the width of the `EditText` to be zero (0dp). Setting the width to zero improves layout performance because using "`wrap_content`" as the width requires the system to calculate a width that is ultimately irrelevant because the weight value requires another width calculation to fill the remaining space.

Figure 3 shows the result when you assign all weight to the `EditText` element.

![EditText_Gravity](/images/edittext_gravity.png)

**Figure 3**. The `EditText` widget is given all the layout weight, so it fills the remaining space in the `LinearLayout`.

Here’s how your complete `content_my.xml` layout file should now look:

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
   xmlns:app="http://schemas.android.com/apk/res-auto"
   xmlns:tools="http://schemas.android.com/tools"
   android:orientation="horizontal"
   android:layout_width="match_parent"
   android:layout_height="match_parent"
   app:layout_behavior="@string/appbar_scrolling_view_behavior"
   tools:showIn="@layout/activity_my">
    <EditText android:id="@+id/edit_message"
        android:layout_weight="1"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="@string/edit_message" />
    <Button
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="@string/button_send" />
</LinearLayout>
```