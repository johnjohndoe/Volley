# Volley: Easy, Fast Networking for Android

Volley is a library that makes networking for Android apps easier and most importantly, faster.


## Google I/O 2013 Video

We'll give an overview of how it works, common patterns that work well with it, and a walkthrough of how you can easily load thumbnail images for your ListView from the network in parallel.

* [Announcement of Volley at Google I/O 2013][google-io-2013-volley]


## Project origin

This repository is a clone of the [original source code][google-repository]. Some modifications to the project setup have been made to allow Gradle usage.

## How to use?

In order to install the library into your **local Maven repository** run the following command:

```bash
$ ./gradlew clean install
```

This will build the library named `volley-1.0.0.aar` which can be found in the local Maven repository. The path for the Maven folder should be:

```bash
~/.m2/repository/com/android/volley/1.0.0/
```

The library can now be referenced in an Android application project in the `app/build.gradle` as follows:

```groovy
dependencies {
    compile 'com.android:volley:1.0.+'
}
```

Make sure to also reference the local Maven repository in your root `build.gradle` as shown here:

```groovy
buildscript {
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:0.9.+'
    }
}

allprojects {
    repositories {
        mavenCentral()
        mavenLocal() // When you forget this, the library will not be found
    }
}
```


[google-io-2013-volley]: https://www.youtube.com/watch?v=yhv8l9F44qo
[google-repository]: https://android.googlesource.com/platform/frameworks/volley/
