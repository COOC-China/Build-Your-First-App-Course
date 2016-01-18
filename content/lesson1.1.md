# Create a Project with Android Studio

1. In Android Studio, create a new project:

	* If you don't have a project opened, in the **Welcome** screen, click **New Project**.

	* If you have a project opened, from the **File** menu, select **New Project**. The Create New Project screen appears.

2. Fill out the fields on the screen, and click **Next**.

	* **Application Name** is the app name that appears to users. For this project, use "My First App."

	* **Company domain** provides a qualifier that will be appended to the package name; Android Studio will remember this qualifier for each new project you create.

	* **Package name** is the fully qualified name for the project (following the same rules as those for naming packages in the Java programming language). Your package name must be unique across all packages installed on the Android system. You can Edit this value independently from the application name or the company domain.

	* **Project location** is the directory on your system that holds the project files.

3. Under **Select the form factors your app will run on**, check the box for **Phone and Tablet**.

# 相关视频

<iframe frameborder="0" width="640" height="498" src="https://v.qq.com/iframe/player.html?vid=q0180meao3b&tiny=0&auto=0" allowfullscreen></iframe>

4. 	For **Minimum SDK**, select **API 8: Android 2.2 (Froyo)**.
	
	>The Minimum Required SDK is the earliest version of Android that your app supports, indicated using the API level. To support as many devices as possible, you should set this to the lowest version available that allows your app to provide its core feature set. If any feature of your app is possible only on newer versions of Android and it's not critical to the app's core feature set, you can enable the feature only when running on the versions that support it (as discussed in Supporting Different Platform Versions).

5. Leave all of the other options (TV, Wear, and Glass) unchecked and click **Next**.

6. Under **Add an activity to <*template*>**, select **Blank Activity** and click **Next**.

7. Under **Customize the Activity**, change the **Activity Name** to *MyActivity*. The **Layout Name** changes to *activity_my*, and the **Title** to *MyActivity*. The **Menu Resource** Name is *menu_my*.

8. Click the **Finish** button to create the project.

Your Android project is now a basic "Hello World" app that contains some default files. 

# 相关视频

<iframe frameborder="0" width="640" height="498" src="https://v.qq.com/iframe/player.html?vid=y01804ziw75&tiny=0&auto=0" allowfullscreen></iframe>