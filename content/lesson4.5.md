# Display the Message

1.	In the `res/layout` directory, edit the `content_display_message.xml` file.

2.	Add an `android:id` attribute to the `RelativeLayout`. You need this attribute to reference the object from your app code.

	```xml
	< RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
	...
	android:id="@+id/content">
	</RelativeLayout>
	```

3.	Switch back to editing `DisplayMessageActivity.java`.

4.	In the `onCreate()` method, create a `TextView` object.

	```java
	TextView textView = new TextView(this);
	```

5.	Set the text size and message with `setText()`.

	```java
	textView.setTextSize(40);
	textView.setText(message);
	```

6.	Add the `TextView` to the `RelativeLayout` identified by `R.id.content`.

	```java
	RelativeLayout layout = (RelativeLayout) findViewById(R.id.content);
	layout.addView(textView);
	```

7.	At the top of the file, import the `TextView` class.

	In Android Studio, press Alt + Enter (option + return on Mac) to import missing classes.

The complete `onCreate()` method for `DisplayMessageActivity` now looks like this:

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   setContentView(R.layout.activity_display_message);
   Toolbar toolbar = (Toolbar) findViewById(R.id.toolbar);
   setSupportActionBar(toolbar);

   FloatingActionButton fab = (FloatingActionButton) findViewById(R.id.fab);
   fab.setOnClickListener(new View.OnClickListener() {
       @Override
       public void onClick(View view) {
           Snackbar.make(view, "Replace with your own action", Snackbar.LENGTH_LONG)
                   .setAction("Action", null)
                   .show();
       }
   });
   getSupportActionBar().setDisplayHomeAsUpEnabled(true);

   Intent intent = getIntent();
   String message = intent.getStringExtra(MyActivity.EXTRA_MESSAGE);
   TextView textView = new TextView(this);
   textView.setTextSize(40);
   textView.setText(message);

   RelativeLayout layout = (RelativeLayout) findViewById(R.id.content);
   layout.addView(textView);
```

You can now run the app. When it opens, type a message in the text field, and click `Send`. The second activity replaces the first one on the screen, showing the message you entered in the first activity.