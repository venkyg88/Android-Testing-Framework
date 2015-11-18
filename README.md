#Android Testing Frameworks


###Table of Contents

 0. [Preface](#preface)
 1. [Introduction](#introduction)
 2. [The Recommended Frameworks](#the-recommended-frameworks)
 3. [How to set up your test environment](#how-to-set-up-your-test-environment)

##Preface
This document describes the recommended frameworks for testing Android applications. The recommended frameworks cover basic unit testing and functional/UI testing.

If you are trying to choose a framework for testing your application or trying to configure your test environment, the following is RA's recommendation for setting up the ideal testing environment.


##Introduction
Mobile applications rely heavily on user experience as a cornerstone of their value, and as such, it is crucial that mobile applications provide exceptional user experience. To insure the best possible user performance, we find it helpful to create tests to insure quality in three key areas:

>	**Unit Tests:** Guarantee the stability of your application's logic in the smallest possible increments

>	**UI/Functional Tests:** Verify the reliability of your application's user interface and user interactions

Each of these areas is critical to the construction of a great user experience, and each is subject to its own unique pitfalls. Use of the following testing frameworks will help to guarantee the best user experience possible.

##The Recommended Frameworks

The Android Testing Support Library provides an extensive framework for testing Android apps. This library provides a set of APIs that allow you to quickly build and run test code for your apps, including JUnit 4 and functional user interface (UI) tests. You can run tests created using these APIs from the Android Studio IDE or from the command line.

<p>The Android Testing Support library is available through the Android SDK Manager.
    For more information, see <a href="https://developer.android.com/tools/testing-support-library/index.html#setup">Testing Support Library Setup</a>
  </p>
  
The Android Testing Support Library includes the following test automation tools:

###AndroidJUnitRunner: 
JUnit 4-compatible test runner for Android. The AndroidJUnitRunner class is a JUnit test runner that lets you run JUnit 3 or JUnit 4-style test classes on Android devices, including those using the Espresso and UI Automator testing frameworks. This class replaces the InstrumentationTestRunner class, which only supports JUnit 3 tests.

<p> For more information on key features, see <a href="https://developer.android.com/tools/testing-support-library/index.html#features">Android JUnitRunner Key Features</a>
  </p>

###Espresso:
UI testing framework; suitable for functional UI testing within an app. The Espresso testing framework provides a set of APIs to build UI tests to test user flows within an app. These APIs let you write automated UI tests that are concise and that run reliably

<p> For more information on key features, see under Espresso<a href="https://developer.android.com/tools/testing-support-library/index.html#features"> Espresso Key Features</a>
  </p>

###UI Automator:
UI testing framework; suitable for cross-app functional UI testing across system and installed apps.
The UI Automator testing framework provides a set of APIs to build UI tests that perform interactions on user apps and system apps. The UI Automator APIs allows you to perform operations such as opening the Settings menu or the app launcher in a test device.

<p> For more information on key features, see under UI Automator<a href="https://developer.android.com/tools/testing-support-library/index.html#features"> UI Automator Key Features</a>
  </p>

##What the decision was guided by (why these frameworks)
In determining which frameworks were best used to create a comprehensive and easy to use suite, a number of frameworks were considered, and judged on several different criteria.
###Unit Testing Tools
| Framework | Scripting Language | Supported API Levels | Installation | Readability | Documentation | Unit Testing |  Functional/UI Testing | Community | Compatibility with Jenkins |
| --------- | -----------------  | -------------------- | ------------ | ----------- | ------------- | ------------ | --------------------- | --------- | -------------------------- |
| AndroidJUnitRunner | Java | All APIs supporting both JUnit3 and JUnit4 | comes with Android Testing Support Library, is available through the Android SDK Manager. Android Studio is recommended | Hamcrest improves readability | https://developer.android.tools/testing-support-library/index.html#AndroidJUnitRunner | Available | N/A | Google | Yes |
| Espresso | Java | 8,10,15-19 | Comes with Android Testing Support Library, is available through the Android SDK Manager and building it through Gradle. Android Studio is recommended. | Allows writing painless UI tests with a nice UI. Hamcrest improves readability of assertions | https://developer.android.com/tools/testing-support-library/index.html#UIAutomator | N/A | Available | Google | Yes |
| UI Automator | Java | 16=> | comes with Android Testing Support Library, is availble through Android SDK. Studio is recommended | The UIAutomatorViewer tool provides a convenient GUI to scan and analyze the UI components currently displayed on an Android device | https://developer.android.com/tools/testing-support-library/index.html#UIAutomator | N/A | Available | Google | Yes |
| Robotium | Java | most of them, delayed support for latest frameworks | https://code.google.com/p/robotium/wiki/Getting_Started | Readability of test cases is greatly improved, compared to standard instrumentation tests | http://robotium.googlecode.com/svn/doc/index.html| N/A | Available | Contributors | Available but sometimes Gradle doesnot download the dependencies automatically, we need to do it manually |
| Appium | Almost any (Java/Ruby preffered) | All, little slow in supporting latest platforms | http://appium.io/slate/en/tutorial/android.html?ruby#install-android | Based on the scripting language used | http://appium.io/slate/en/tutorial/android.html?ruby#native-android-automation | N/A | Availabel | Active | Available, appium.io/slate/en/tutorial/android.html?ruby#running-locally |


####In conclusion#

Having reviewed the above frameworks, AndroidJUnitRunner, Espresso, and UIAutomator were selected based on the below reasons -
- Ease of installion 
- Google's continuous support on future versions.
- Small learning curve.
- Developer's familarity with JUNit and Instrumentation.

##How to set up your test environment

Prerequisites
--------------
- Android SDK v22
- Android Build Tools v22
- Android Support Repository rev13

Getting Started
---------------

These samples use the Gradle build system. To build a project, enter the project directory and use the `./gradlew assemble` command or use "Import Project" in Android Studio.

- Use `./gradlew connectedAndroidTest` to run the tests on a connected emulator or device.
- Use `./gradlew test` to run the unit test on your local host.

There is a top-level `build.gradle` file if you want to build and test all samples from the root directory. This is mostly helpful to build on a CI (Continuous Integration) server.
