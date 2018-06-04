# Mobile Automation Challenge


## Installation Instructions for Android SDK and Appium (MacOS)
### 1 - Install latest Android SDK
	https://developer.android.com/studio/install.html

### 2 - The installer will install Android SDK in the following location
	/Users/<YOUR-USERNAME>/Library/Android/sdk

### 3 - Edit your .bash_profile to have the following:

	export ANDROID_HOME=/Users/<YOUR-USERNAME>/Library/Android/sdk
	export ANDROID_SDK_ROOT=$ANDROID_HOME
	export JAVA_HOME=$(/usr/libexec/java_home)

	PATH=$PATH:$ANDROID_SDK_ROOT/tools/bin
	PATH=$PATH:$ANDROID_SDK_ROOT/emulator
	PATH=$PATH:$ANDROID_SDK_ROOT/platform-tools
	PATH=$PATH:$JAVA_HOME/bin

Your .bash_profile should be in ~/.bash_profile

If you don't have a .bash_profile then run this command to create it: touch ~/.bash_profile

To edit your .bash_profile run: sudo nano ~/.bash_profile

### 4 - Install latest platform tools by running the following command in a terminal ###
	sdkmanager "platform-tools" "platforms;android-26"

### 5 - download necessary packages ###
	sdkmanager "system-images;android-26;google_apis;x86"

### 6 - Create an avd with a name TestAvd - Android Virtual Device ###
	avdmanager create avd -n TestEmulator -k "system-images;android-26;google_apis;x86" -d "Nexus 5X"

### 7 - Launch the emulator to see if everything is working
	emulator -avd TestEmulator -skin 1440x2560

### 8 - Now install appium
	npm install -g appium

### 9 - Install WebDriver packages
npm install wd

### 10 - Start the appium server by running the following command
	appium

### 11 Install BookSearch Test App
To install an BookSearch.apk file on the emulated device, drag an APK file onto the emulator screen.
An APK Installer dialog appears.
When the installation completes, you can view the app in your apps list.
<br />
<img src="screenshots/BookSearchApp.png" width="200">

## Challenge Question:
1. We are developing an MVP of a BookSearch mobile app.
For this MVP we only have simple searching capabilities where results of the books
are returned correctly according to search keywords.
2. Knowing that searching logic has been tested thoroughly with unit tests,
which tests would you write to ensure our end users are satisfied with the functionality of the app.  Write out the tests in any format
3. Pick a couple of tests from #2 and using Appium (granted you completed Installation steps above), the language of your choice (Node/Javascript preferred) send us the code (we don't expect you to spend more than a couple hours on this exercise)
