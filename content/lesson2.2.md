# Run on the Emulator

Whether you're using Android Studio or the command line, to run your app on the emulator you need to first create an Android Virtual Device (AVD). An AVD is a device configuration for the Android emulator that allows you to model a specific device.

### Create an AVD

1. Launch the Android Virtual Device Manager:

	* In Android Studio, select **Tools > Android > AVD Manager**, or click the AVD Manager icon  in the toolbar. The *AVD Manager* screen appears.

	* Or, from the command line, change directories to *sdk/* and execute:
	```bash
	tools/android avd
	```
	
	> **Note**: The AVD Manager that appears when launched from the command line is different from the version in Android Studio, so the following instructions may not all apply.

2. On the AVD Manager main screen, click **Create Virtual Device**.

3. In the Select Hardware window, select a device configuration, such as Nexus 6, then click **Next**.

4. Select the desired system version for the AVD and click **Next**.

5. Verify the configuration settings, then click **Finish**.

For more information about using AVDs, see Managing AVDs with AVD Manager.

### Run the app from Android Studio

1. In **Android Studio**, select your project and click **Run** from the toolbar.

2. In the **Choose Device** window, click the **Launch emulator** radio button.

3. From the **Android virtual device** pull-down menu, select the emulator you created, and click **OK**.

It can take a few minutes for the emulator to load itself. You may have to unlock the screen. When you do, My First App appears on the emulator screen.

### Run your app from the command line

1. Build the project from the command line. The output APK for the app module is located in
```
	app/build/outputs/apk/.
```

2. Make sure the Android SDK `platform-tools/` directory is included in your `PATH` environment variable.

3. Execute this command:
	```
	$ adb install app/build/outputs/apk/apk-debug.apk
	```

4. On the emulator, locate *MyFirstApp* and open it.