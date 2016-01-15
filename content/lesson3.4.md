# Add a Button

1.	In Android Studio, from the `res/layout` directory, edit the `content_my.xml` file.

2.	Within the <`LinearLayout`> element, define a <`Button`> element immediately following the <`EditText`> element.

3.	Set the button's width and height attributes to "`wrap_content`" so the button is only as big as necessary to fit the button's text label.

4.	Define the button's text label with the `android:text` attribute; set its value to the `button_send` string resource you defined in the previous section.

Your <`LinearLayout`> should look like this:

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:orientation="horizontal"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:layout_behavior="@string/appbar_scrolling_view_behavior"
    tools:showIn="@layout/activity_my">
        <EditText android:id="@+id/edit_message"
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:hint="@string/edit_message" />
        <Button
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:text="@string/button_send" />
</LinearLayout>
```

>**Note**: This button doesn't need the `android:id` attribute, because it won't be referenced from the activity code.

The layout is currently designed so that both the EditText and Button widgets are only as big as necessary to fit their content, as Figure 2 shows.

![EditText_Wrap.png](/images/edittext_wrap.png)

**Figure 2**. The `EditText` and `Button` widgets have their widths set to "`wrap_content`".

This works fine for the button, but not as well for the text field, because the user might 
type something longer. It would be nice to fill the unused screen width with the text field.
 You can do this inside a `inearLayout` with the weight property, which you can specify using
  the `android:layout_weight` attribute.

The weight value is a number that specifies the amount of remaining space each view should 
consume, relative to the amount consumed by sibling views. This works kind of like the amount
 of ingredients in a drink recipe: "2 parts soda, 1 part syrup" means two-thirds of the drink
  is soda. For example, if you give one view a weight of 2 and another one a weight of 1, the
   sum is 3, so the first view fills 2/3 of the remaining space and the second view fills the
    rest. If you add a third view and give it a weight of 1, then the first view (with weight
     of 2) now gets 1/2 the remaining space, while the remaining two each get 1/4.

The default weight for all views is 0, so if you specify any weight value greater than 0 to 
only one view, then that view fills whatever space remains after all views are given the 
space they require.