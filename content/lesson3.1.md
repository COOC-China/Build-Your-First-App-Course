# Create a Linear Layout

1. In Android Studio, from the `res/layout` directory, open the `content_my.xml` file.

	The BlankActivity template you chose when you created this project includes the `content_my.xml` file with a `RelativeLayout` root view and a `TextView` child view.

2. In the **Preview** pane, click the Hide icon  to close the Preview pane.

	In Android Studio, when you open a layout file, you’re first shown the Preview pane. Clicking elements in this pane opens the WYSIWYG tools in the Design pane. For this lesson, you’re going to work directly with the XML.

3. Delete the `<TextView>` element.

4. Change the `<RelativeLayout>` element to `<LinearLayout>`.

5. Add the `android:orientation` attribute and set it to `"horizontal"`.

6. Remove the `android:padding` attributes and the `tools:context` attribute.

The result looks like this:

```xml
	<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
		xmlns:app="http://schemas.android.com/apk/res-auto"
		xmlns:tools="http://schemas.android.com/tools"
		android:orientation="horizontal"
		android:layout_width="match_parent"
		android:layout_height="match_parent"
		app:layout_behavior="@string/appbar_scrolling_view_behavior"
		tools:showIn="@layout/activity_my">
```


`LinearLayout` is a view group (a subclass of `ViewGroup`) that lays out child views in either a vertical or horizontal orientation, as specified by the `android:orientation` attribute. Each child of a `LinearLayout` appears on the screen in the order in which it appears in the XML.

Two other attributes, `android:layout_width` and `android:layout_height`, are required for all views in order to specify their size.

Because the `LinearLayout` is the root view in the layout, it should fill the entire screen area that's available to the app by setting the width and height to `"match_parent"`. This value declares that the view should expand its width or height to match the width or height of the parent view.

For more information about layout properties, see the `Layout` guide.