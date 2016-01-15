# Build an Intent

1.	In `MyActivity.java`, inside the `sendMessage()` method, create an `Intent` to start an activity called `DisplayMessageActivity` with the following code:

	java/com.mycompany.myfirstapp/MyActivity.java

	```java
	public void sendMessage(View view) {
	  Intent intent = new Intent(this, DisplayMessageActivity.class);
	}
	```

	>**Note**: The reference to `DisplayMessageActivity` will raise an error if you’re using an IDE such as Android Studio because the class doesn’t exist yet. Ignore the error for now; you’ll create the class soon.

	The constructor used here takes two parameters:

	* A `Context` as its first parameter (`this` is used because the `Activity` class is a subclass of `Context`)

	* The `Class` of the app component to which the system should deliver the `Intent` (in this case, the activity that should be started)

	Android Studio indicates that you must import the `Intent` class.

2.	At the top of the file, import the `Intent` class:

	java/com.mycompany.myfirstapp/MyActivity.java

	```java
	import android.content.Intent;
	```

	>**Tip**: In Android Studio, press Alt + Enter (option + return on Mac) to import missing classes.

3.	Inside the `sendMessage()` method, use `findViewById()` to get the `EditText` element.

	java/com.mycompany.myfirstapp/MyActivity.java

	```java
	public void sendMessage(View view) {
	  Intent intent = new Intent(this, DisplayMessageActivity.class);
	  EditText editText = (EditText) findViewById(R.id.edit_message);
	}
	```

4.	At the top of the file, import the `EditText` class.

	In Android Studio, press Alt + Enter (option + return on Mac) to import missing classes.

5.	Assign the text to a local `message` variable, and use the `putExtra()` method to add its text value to the intent.

	java/com.mycompany.myfirstapp/MyActivity.java

	```java
	public void sendMessage(View view) {
	  Intent intent = new Intent(this, DisplayMessageActivity.class);
	  EditText editText = (EditText) findViewById(R.id.edit_message);
	  String message = editText.getText().toString();
	  intent.putExtra(EXTRA_MESSAGE, message);
	}
	```

	An `Intent` can carry data types as key-value pairs called extras. The `putExtra()` method takes the key name in the first parameter and the value in the second parameter.

6.	At the top of the `MyActivity` class, add the `EXTRA_MESSAGE` definition as follows:

	java/com.mycompany.myfirstapp/MyActivity.java

	```java
	public class MyActivity extends AppCompatActivity {
	    public final static String EXTRA_MESSAGE = "com.mycompany.myfirstapp.MESSAGE";
	    ...
	}
	```

	For the next activity to query the extra data, you should define the key for your intent's extra using a public constant. It's generally a good practice to define keys for intent extras using your app's package name as a prefix. This ensures the keys are unique, in case your app interacts with other apps.

7.	In the `sendMessage()` method, to finish the intent, call the `startActivity()` method, passing it the `Intent` object created in step 1.

	With this new code, the complete `sendMessage()` method that's invoked by the Send button now looks like this:

	java/com.mycompany.myfirstapp/MyActivity.java

	```java
	/** Called when the user clicks the Send button */
	public void sendMessage(View view) {
	    Intent intent = new Intent(this, DisplayMessageActivity.class);
	    EditText editText = (EditText) findViewById(R.id.edit_message);
	    String message = editText.getText().toString();
	    intent.putExtra(EXTRA_MESSAGE, message);
	    startActivity(intent);
	}
	```

	The system receives this call and starts an instance of the `Activity` specified by the Intent. Now you need to create the `DisplayMessageActivity` class in order for this to work.