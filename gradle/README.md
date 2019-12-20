# KotlinJavaDocMavenPush
kotlin_maven_push.gradle: Kotlin Javadoc of Android library for Bintray maven push.

为支持Kotlin语言Android库提供的生成Javadoc的kotlin_maven_push.gradle.



# Getting Started



#### Step 1: Apply the plugin to your Gradle build script of `android-maven-gradle-plugin`, `gradle-bintray-plugin`, `dokka-android-gradle-plugin`:

build.gradle in root project:

```
buildscript {
    repositories {
        google()
        jcenter()
    }
    dependencies {
        classpath 'com.android.tools.build:gradle:3.1.2

        classpath 'com.github.dcendents:android-maven-gradle-plugin:2.0'
        classpath 'com.jfrog.bintray.gradle:gradle-bintray-plugin:1.7.3'
        classpath "org.jetbrains.dokka:dokka-android-gradle-plugin:${dokka_version}"
    }
}
```



#### Step 2: apply `kotlin_maven_push.gradle` in your library module: 

build.gradle in library module:

```

//Append this at the end of build.gradle
apply from: 'https://raw.github.com/Ayvytr/KotlinJavadocMavenPush/master/kotlin_maven_push.gradle'
```

**Note: If you use apply to import a gradle file, you need add `raw` and remove `blob` in path.**

#### Step 3:  Add Bintray config in gradle.properties in your library module, such as [gradle.properties](https://github.com/Ayvytr/EasyKotlin/blob/master/EasyKotlin/gradle.properties)



#### Step 4: Config Bintray account user and key in local.properties in your root project directory:

```
BINTRAY_USER=your username
BINTRAY_KEY=your key
```



#### Step 5:  Run task `gradlew install`, and you will get your Kotlin library Javadoc.

#### Step 6: Run task `gradlew bintrayUpload`, to upload your library.



## See more options as follow:

* https://github.com/bintray/gradle-bintray-plugin
* https://github.com/dcendents/android-maven-gradle-plugin
* https://github.com/Kotlin/dokka
