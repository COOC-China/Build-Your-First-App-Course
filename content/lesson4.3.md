#Create the Second Activity

All subclasses of `Activity` must implement the `onCreate()` method. This method is where the activity receives the intent with the message, then renders the message. Also, the `onCreate()` method must define the activity layout with the `setContentView()` method. This is where the activity performs the initial setup of the activity components.

### Create a new activity using Android Studio

Android Studio includes a stub for the `onCreate()` method when you create a new activity. The *New Android Activity* window appears.

1.  In Android Studio, in the `java` directory, select the package, `com.mycompany.myfirstapp`, right-click, and select `New > Activity > Blank Activity`.

2.  In the `Choose options` window, fill in the activity details:

    * **Activity Name**: DisplayMessageActivity
    * **Layout Name**: activity_display_message
    * **Title**: My Message
    * **Hierarchical Parent**: com.mycompany.myfirstapp.MyActivity
    * **Package name**: com.mycompany.myfirstapp

    Click **Finish**.

3.  Open the `DisplayMessageActivity.java` file.

    The class already includes an implementation of the required `onCreate()` method. You update the implementation of this method later.

If you're developing with Android Studio, you can run the app now, but not much happens. Clicking the Send button starts the second activity, but it uses a default "Hello world" layout provided by the template. You'll soon update the activity to instead display a custom text view.

### Create the activity without Android Studio

If you're using a different IDE or the command line tools, do the following:

1.  Create a new file named `DisplayMessageActivity.java` in the project's `src/` directory, next to the original `MyActivity.java` file.

2.  Add the following code to the file:

    ```java
    public class DisplayMessageActivity extends AppCompatActivity {

        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate(savedInstanceState);
            setContentView(R.layout.activity_display_message);

            if (savedInstanceState == null) {
                getSupportFragmentManager().beginTransaction()
                    .add(R.id.container, new PlaceholderFragment()).commit();
            }
        }

        @Override
        public boolean onOptionsItemSelected(MenuItem item) {
            // Handle app bar item clicks here. The app bar
            // automatically handles clicks on the Home/Up button, so long
            // as you specify a parent activity in AndroidManifest.xml.
            int id = item.getItemId();
            if (id == R.id.action_settings) {
                return true;
            }
            return super.onOptionsItemSelected(item);
        }

        /**
         * A placeholder fragment containing a simple view.
         */
        public static class PlaceholderFragment extends Fragment {

            public PlaceholderFragment() { }

            @Override
            public View onCreateView(LayoutInflater inflater, ViewGroup container,
                      Bundle savedInstanceState) {
                  View rootView = inflater.inflate(R.layout.fragment_display_message,
                          container, false);
                  return rootView;
            }
        }
    }
    ```

    >**Note**: If you are using an IDE other than Android Studio, your project does not contain the `activity_display_message` layout that's requested by `setContentView()`. That's OK because you will update this method later and won't be using that layout.

3.  To your `strings.xml` file, add the new activity's title as follows:

    ```xml
    <resources>
        ...
        <string name="title_activity_display_message">My Message</string>
    </resources>
    ```

4.  In your manifest file, `AndroidManifest.xml`, within the `Application` element, add the <`activity`> element for your `DisplayMessageActivity` class, as follows:

    ```xml
    <application ... >
        ...
        <activity
            android:name="com.mycompany.myfirstapp.DisplayMessageActivity"
            android:label="@string/title_activity_display_message"
            android:parentActivityName="com.mycompany.myfirstapp.MyActivity" >
            <meta-data
                android:name="android.support.PARENT_ACTIVITY"
                android:value="com.mycompany.myfirstapp.MyActivity" />
        </activity>
    </application>
    ```

The `android:parentActivityName` attribute declares the name of this activity's parent activity within the app's logical hierarchy. The system uses this value to implement default navigation behaviors, such as `Up navigation` on Android 4.1 (API level 16) and higher. You can provide the same navigation behaviors for older versions of Android by using the `Support Library` and adding the <`meta-data`> element as shown here.

>**Note**: Your Android SDK should already include the latest Android Support Library, which you installed during the `Adding SDK Packages` step. When using the templates in Android Studio, the Support Library is automatically added to your app project (you can see the library's JAR file listed under Android Dependencies). If you're not using Android Studio, you need to manually add the library to your project—follow the guide for `setting up the Support Library` then return here.

If you're using a different IDE than Android Studio, don't worry that the app won't yet compile. You'll soon update the activity to display a custom text view.