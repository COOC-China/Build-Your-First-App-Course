# Run on a Real Device

If you have a device running Android, here's how to install and run your app.

### Set up your device

1. Plug in your device to your development machine with a USB cable. If you're developing on Windows, you might need to install the appropriate USB driver for your device. For help installing drivers, see the OEM USB Drivers document.

2. Enable **USB debugging** on your device.

	* On most devices running Android 3.2 or older, you can find the option under **Settings > Applications > Development**.

	* On Android 4.0 and newer, it's in **Settings > Developer options**.

	> **Note**: On Android 4.2 and newer, **Developer options** is hidden by default. To make it available, go to **Settings > About phone** and tap **Build number** seven times. Return to the previous screen to find **Developer options**.

### Run the app from Android Studio

1. Select one of your project's files and click **Run** from the toolbar.

2. In the **Choose Device** window that appears, select the **Choose a running device** radio button, select your device, and click **OK** .

Android Studio installs the app on your connected device and starts it.

### Run the app from a command line

Open a command-line and navigate to the root of your project directory. Use Gradle to build your project in debug mode, invoke the `assembleDebug` build task using the Gradle wrapper script (`gradlew assembleRelease`).

This creates your debug `.apk` file inside the module `build/` directory, named `app-debug.apk`.

On Windows platforms, type this command:

```bash
	> gradlew.bat assembleDebug
```

On Mac OS and Linux platforms, type these commands:

```bash
$ chmod +x gradlew
$ ./gradlew assembleDebug
```

After you build the project, the output APK for the app module is located in `app/build/outputs/apk/`

> **Note**: The first command (`chmod`) adds the execution permission to the Gradle wrapper script and is only necessary the first time you build this project from the command line.

Make sure the Android SDK `platform-tools/` directory is included in your `PATH` environment variable, then execute:

```bash
	$ adb install app/build/outputs/apk/app-debug.apk
```

On your device, locate *MyFirstApp* and open it.

That's how you build and run your Android app on a device! To start developing, continue to the next lesson.