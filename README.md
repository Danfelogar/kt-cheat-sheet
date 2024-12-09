# Cheat Sheet for "Associate Android Developer certification" in Kotlin

This is a guie brown whit the propose to help me and others when you need to review all or kind all lesson in the official documentation of kotlin by google, i take inspiration in this other project [Kotlin-cheat-sheet](https://github.com/alidehkhodaei/kotlin-cheat-sheet?tab=readme-ov-file) by [Ali Dehkhodaei](https://github.com/alidehkhodaei) and if this content was useful for you i achievement to give one ⭐ in his repository also you learn with more details in the [Training courses](https://developer.android.com/courses) what gif google for prepare the exam.I apologize in advance because I also use this space to practice my english😅.

![](assets/imgs/kotlin-intro-logo.jpg)

# Table of Contents

- [Android Basics with Compose (lvl: Beginner)](#Android-Basics-with-Compose-(lvl:-Beginner))
  - [Unit 1: Your first Android app](#Unit-1:-Your-first-Android-app)
    - [Introduction to Kotlin](#Introduction-to-Kotlin)
      - [Create and use variables in Kotlin](#Create-and-use-variables-in-Kotlin)
    - [Build a basic layout](#Build-a-basic-layout)
      - [Build a simple app with text composables](#Build-a-simple-app-with-text-composables)
      - [Add images to your Android app](#Add-images-to-your-Android-app)
  - [Unit 2: Building app UI](#Unit-2:-Building-app-UI)



# Android Basics with Compose (lvl: Beginner)

## Unit 1: Your first Android app
## Introduction to Kotlin
### Create and use variables in Kotlin
#### **Data types**
 When you decide what aspects of your app can be variable, it's important to specify what type of data can be stored in those variables. In Kotlin, there are some common basic data types. The table below shows a different data type in each row. For each data type, there's a description of what kind of data it can hold and example values.

![](assets/imgs/data-types-table.png)
If you need to update the value of a variable, declare the variable with the Kotlin keyword `var`, instead of `val`

* `val` keyword - Use when you expect the variable value will not change.
* `var` keyword - Use when you expect the variable value can change.
#### **Commenting in your code(examples)**
``// This is a comment.``
```
/*
 * This is a very long comment that can
 * take up multiple lines.
 */
 ```

## Build a basic layout
### Build a simple app with text composables

#### **Composable functions**
Composable functions are the basic building block of a UI in Compose. A composable function:

* Describes some part of your UI.
* Doesn't return anything.
* Takes some input and generates what's shown on the screen.
example:
```
@Preview(showBackground = true)
@Composable
fun BirthdayCardPreview() {
    HappyBirthdayTheme {
        Greeting("Android")
    }
}
```
The Composable function is annotated with the `@Composable` annotation; this annotation informs the Compose compiler that this function is intended to convert data into UI.
#### **Arrange the text elements in a row and column**
The three basic standard layout elements in Compose are `Column`, `Row`, and `Box`. They are Composable functions that take Composable content, so you can place items inside. For example, each child within a `Row` will be placed horizontally next to each other.
![](assets/imgs/example-arrange-the-text-elements.png)
### Add images to your Android app
* The `Resource Manager` tab in Android Studio helps you add and organize your images and other resources.
```
val image = painterResource(R.drawable.androidparty)
```
* An `Image` composable is a UI element that displays images in your app.
* An `Image` composable should have a content description to make your app more accessible.
```
Image(
    painter = image,
    contentDescription = null,
    contentScale = ContentScale.Crop
)
```
* Text that's shown to the user, such as the birthday greeting, should be extracted into a string resource to make it easier to translate your app into other languages.

