# Receive the Intent

Every `Activity` is invoked by an `Intent`, regardless of how the user navigated there. You can get the `Intent` that started your activity by calling `getIntent()` and retrieve the data contained within the intent.

1.	In the `java/com.mycompany.myfirstapp` directory, edit the `DisplayMessageActivity.java` file.

2.	Get the intent and assign it to a local variable.

	```java
	Intent intent = getIntent();
	```

3.	At the top of the file, import the `Intent` class.

	In Android Studio, press Alt + Enter (option + return on Mac) to import missing classes.

4.	Extract the message delivered by `MyActivity` with the `getStringExtra()` method.
	```java
	String message = intent.getStringExtra(MyActivity.EXTRA_MESSAGE);
	```