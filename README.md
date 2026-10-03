# EmotiLog

A small native Android mood-logging app built in Java for CMPUT 301. Users record one of six emotions, review the session log, and view per-emotion counts.

<p align="center">
  <img src="EmotiLog/code/EmotiLog/app/src/main/res/drawable/happy.png" alt="EmotiLog icon" width="90" />
</p>

## Implemented features

- six one-tap emotions: Happy, Sad, Angry, Tired, InLove, and Chill
- automatic timestamps in <code>yyyy-MM-dd HH:mm:ss</code> format
- newest-first session log
- per-emotion counts and total count
- three-screen navigation: Home, Logs, and Summary
- Android View Binding and Jetpack Navigation

## How it works

The application is intentionally simple:

- <code>HomeFragment</code> reads each emotion button's content description and sends it to <code>Logger.log(...)</code>
- <code>Logger</code> stores timestamped entries in an in-memory <code>ArrayList</code>
- <code>LogsFragment</code> renders a copy of the stored entries
- <code>SummaryLogger</code> derives counts from those entries
- <code>SummaryFragment</code> refreshes the counts when the screen resumes

**Persistence:** entries live in process memory only. Closing/restarting the app process clears the log; there is no database or file persistence in the current source.

## Screenshots

| Home | Logs | Summary |
|---|---|---|
| ![Home](EmotiLog/doc/Home_Screen.png) | ![Logs](EmotiLog/doc/Logs.png) | ![Summary](EmotiLog/doc/Summary_Page.png) |

## Tech stack

- Java 11
- Android SDK (min SDK 24, target/compile SDK 36)
- AndroidX / Material Components
- Jetpack Navigation
- View Binding
- JUnit / AndroidX test dependencies

## Project layout

~~~text
EmotiLog/
└── EmotiLog/
    └── code/
        └── EmotiLog/
            ├── app/
            │   ├── src/main/java/com/example/emotilog/
            │   │   ├── MainActivity.java
            │   │   ├── Logger.java
            │   │   ├── SummaryLogger.java
            │   │   └── ui/
            │   └── src/main/res/
            └── build.gradle.kts
~~~

The repository also includes UML/documentation assets and a recorded demonstration.

## Run locally

~~~bash
git clone https://github.com/muhzain05/EmotiLog.git
cd EmotiLog/EmotiLog/code/EmotiLog
~~~

Open that Android project in Android Studio, sync Gradle, and run it on an emulator or Android device.

## Author

Muhammad Zain Asad — [GitHub](https://github.com/muhzain05)
