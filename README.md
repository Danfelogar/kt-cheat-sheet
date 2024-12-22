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
    - [Kotlin fundamentals](#Kotlin-fundamentals)
      - [Write conditionals in Kotlin](#Write-conditionals-in-Kotlin)
      - [Use classes and objects in Kotlin](#Use-classes-and-objects-in-Kotlin)
      - [Use function types and lambda expressions in Kotlin](#Use-function-types-and-lambda-expressions-in-Kotlin)
    - [Add a button to an app](#Add-a-button-to-an-app)
    - [Interacting with UI and state](#Interacting-with-UI-and-state)
      -[Intro to state in Compose](#Intro-to-state-in-Compose)
      -[Write automated tests](#Write-automated-tests)
- [Android quizzes (lvl: Beginner)](#Android-quizzes-(lvl:-Beginner))
  - [Unit 1:](#Unit-1:)
    - [Introduction to Kotlin(quiz 1)](#Introduction-to-Kotlin(quiz-1))
    - [Setup Android Studio(quiz 2)](#Setup-Android-Studio(quiz-2))
    - [Build a basic layout(quiz 3)](#Build-a-basic-layout(quiz-2))
  - [Unit 2:](#Unit-2:)
    - [Kotlin fundamentals(quiz 1)](#Kotlin-fundamentals(quiz-1))
    - [Add a button to an app(quiz 2)](#Add-a-button-to-an-app(quiz-2))
    - [Interacting with UI and state(quiz 3)](#Interacting-with-UI-and-state(quiz 3))

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

## Unit 2: Building app UI
## Kotlin fundamentals
### Write conditionals in Kotlin
#### **Use if/else statements to express conditions**
After the closing curly brace of the `if` statement, you add the `else` keyword followed by a pair of curly braces. Inside the curly braces of the `else` statement, you can add a second body that only executes when the condition in the `if` branch is false.

The `else` branch is always located at the end of an `if/else` statement because it's a catchall branch. It automatically executes when all other conditions in the preceding branches aren't satisfied. As such, the `else` branch isn't suitable when you want an action to execute only when it satisfies a specific condition. In the case of the traffic light, you can use the `else if` branch to specify the condition for green lights.
* Example:
```
fun main() {
    val trafficLightColor = "Black"

    if (trafficLightColor == "Red") {
        println("Stop")
    } else if (trafficLightColor == "Yellow") {
        println("Slow")
    } else if (trafficLightColor == "Green") {
        println("Go")
    } else {
        println("Invalid traffic-light color")
    }
}
```
#### **Use a when statement for multiple branches**
In Kotlin, when you deal with multiple branches, you can use the `when` statement instead of the `if/else` statement because it improves readability, which refers to how easy it is for human readers, typically developers, to read the code. It's very important to consider readability when you write your code because it's likely that other developers need to review and modify your code throughout its lifetime. Good readability ensures that developers can correctly understand your code and don't inadvertently introduce bugs into it.
* Example:
```
fun main() {
    val x: Any = 20

    when (x) {
        2, 3, 5, 7 -> println("x is a prime number between 1 and 10.")
        in 1..10 -> println("x is a number between 1 and 10, but not a prime number.")
        is Int -> println("x is an integer number, but not between 1 and 10.")
        else -> println("x isn't an integer number.")
    }
}
```
#### **Summary**
* In Kotlin, branching can be achieved with `if/else` or `when` conditionals.
* The body of an `if` branch in an `if/else` conditional is only executed when the boolean expression inside the `if` branch condition returns a `true` value.
* Subsequent `else if` branches in an `if/else` conditional get executed only when previous `if` or `else if` branches return `false` values.
* The final `else` branch in an `if/else` conditional only gets executed when all previous if or `else if` branches return `false` values.
* It's recommended to use the `when` conditional to replace an `if/else` conditional when there are more than two branches.
* You can write more complex conditions in `when` conditionals with the comma `(,)`, `in` ranges, and the `is` keyword.
* `if/else` and `when` conditionals can work as either statements or expressions.

### Use nullability in Kotlin
#### **Summary**
* A variable can be set to `null` to indicate that it holds no value.
* Non-nullable variables cannot be assigned `null`.
* Nullable variables can be assigned `null`.
* To access methods or properties of nullable variables, you need to use `?.` safe-call operators or `!!` not-null assertion operators.
* You can use `if/else` statements with `null` checks to access nullable variables in non-nullable contexts.
* You can convert a nullable variable to a non-nullable type with `if/else` expressions.
* You can provide a default value for when a nullable variable is `null` with the `if/else` expression or the `?:` Elvis operator.

### Use classes and objects in Kotlin
#### **Define a class**
When you define a class, you specify the properties and methods that all objects of that class should have.

A class definition starts with the `class` keyword, followed by a name and a set of curly braces. The part of the syntax before the opening curly brace is also referred to as the class header. In the curly braces, you can specify properties and functions for the class.

A class consists of three major parts:

* `Properties.` Variables that specify the attributes of the class's objects.
* `Methods.` Functions that contain the class's behaviors and actions.
* `Constructors.` A special member function that creates instances of the class throughout the program in which it's defined.

#### **Define a constructor**
The primary purpose of the constructor is to specify how the objects of the class are created. In other words, constructors initialize an object and make the object ready for use. You did this when you instantiated the object. The code inside the constructor executes when the object of the class is instantiated. You can define a constructor with or without parameters.
#### **Specify appropriate visibility modifiers**
This table helps you determine the appropriate visibility modifiers based on where the property or methods of a class or constructor should be accessible:
![](assets/imgs/visibility-types-table.png)

* Example:
```
import kotlin.properties.ReadWriteProperty
import kotlin.reflect.KProperty

open class SmartDevice(val name: String, val category: String) {

    var deviceStatus = "online"
        protected set

    open val deviceType = "unknown"

    open fun turnOn() {
        deviceStatus = "on"
    }

    open fun turnOff() {
        deviceStatus = "off"
    }
}

class SmartTvDevice(deviceName: String, deviceCategory: String) :
    SmartDevice(name = deviceName, category = deviceCategory) {

    override val deviceType = "Smart TV"

    private var speakerVolume by RangeRegulator(initialValue = 2, minValue = 0, maxValue = 100)

    private var channelNumber by RangeRegulator(initialValue = 1, minValue = 0, maxValue = 200)

    fun increaseSpeakerVolume() {
        speakerVolume++
        println("Speaker volume increased to $speakerVolume.")
    }

    fun nextChannel() {
        channelNumber++
        println("Channel number increased to $channelNumber.")
    }

    override fun turnOn() {
        super.turnOn()
        println(
            "$name is turned on. Speaker volume is set to $speakerVolume and channel number is " +
                "set to $channelNumber."
        )
    }

    override fun turnOff() {
        super.turnOff()
        println("$name turned off")
    }
}

class SmartLightDevice(deviceName: String, deviceCategory: String) :
    SmartDevice(name = deviceName, category = deviceCategory) {

    override val deviceType = "Smart Light"

    private var brightnessLevel by RangeRegulator(initialValue = 0, minValue = 0, maxValue = 100)

    fun increaseBrightness() {
        brightnessLevel++
        println("Brightness increased to $brightnessLevel.")
    }

    override fun turnOn() {
        super.turnOn()
        brightnessLevel = 2
        println("$name turned on. The brightness level is $brightnessLevel.")
    }

    override fun turnOff() {
        super.turnOff()
        brightnessLevel = 0
        println("Smart Light turned off")
    }
}

class SmartHome(
    val smartTvDevice: SmartTvDevice,
    val smartLightDevice: SmartLightDevice
) {

    var deviceTurnOnCount = 0
        private set

    fun turnOnTv() {
        deviceTurnOnCount++
        smartTvDevice.turnOn()
    }

    fun turnOffTv() {
        deviceTurnOnCount--
        smartTvDevice.turnOff()
    }

    fun increaseTvVolume() {
        smartTvDevice.increaseSpeakerVolume()
    }

    fun changeTvChannelToNext() {
        smartTvDevice.nextChannel()
    }

    fun turnOnLight() {
        deviceTurnOnCount++
        smartLightDevice.turnOn()
    }

    fun turnOffLight() {
        deviceTurnOnCount--
        smartLightDevice.turnOff()
    }

    fun increaseLightBrightness() {
        smartLightDevice.increaseBrightness()
    }

    fun turnOffAllDevices() {
        turnOffTv()
        turnOffLight()
    }
}

class RangeRegulator(
    initialValue: Int,
    private val minValue: Int,
    private val maxValue: Int
) : ReadWriteProperty<Any?, Int> {

    var fieldData = initialValue

    override fun getValue(thisRef: Any?, property: KProperty<*>): Int {
        return fieldData
    }

    override fun setValue(thisRef: Any?, property: KProperty<*>, value: Int) {
        if (value in minValue..maxValue) {
            fieldData = value
        }
    }
}

fun main() {
    var smartDevice: SmartDevice = SmartTvDevice("Android TV", "Entertainment")
    smartDevice.turnOn()

    smartDevice = SmartLightDevice("Google Light", "Utility")
    smartDevice.turnOn()
}
```
#### **summary**
* There are four main principles of OOP: encapsulation, abstraction, inheritance, and polymorphism.
* Classes are defined with the `class` keyword, and contain properties and methods.
* Properties are similar to variables except properties can have custom getters and setters.
* A constructor specifies how to instantiate objects of a class.
* You can omit the `constructor` keyword when you define a primary constructor.
* Inheritance makes it easier to reuse code.
* The IS-A relationship refers to inheritance.
* The HAS-A relationship refers to composition.
* Visibility modifiers play an important role in the achievement of encapsulation.
* Kotlin provides four visibility modifiers: the `public`, `private`, `protected`, and `internal` modifiers.
* A property delegate lets you reuse the getter and setter code in multiple classes.

### Use function types and lambda expressions in Kotlin
#### **Write lambda expressions with shorthand syntax**
Lambda expressions provide a variety of ways to make your code more concise. You explore a few of them in this section because most of the lambda expressions that you encounter and write are written with shorthand syntax.
**Omit parameter name**
When you wrote the `coins()` function, you explicitly declared the name `quantity` for the function's `Int` parameter. However, as you saw with the `cupcake()` function, you can omit the parameter name entirely. When a function has a single parameter and you don't provide a name, Kotlin implicitly assigns it the `it` name, so you can omit the parameter name and `->` symbol, which makes your lambda expressions more concise. The syntax is illustrated in this image:
![](assets/imgs/lambda-expressions-with-shorthand-syntax.png)

**Summary**
* Functions in Kotlin are first-class constructs and can be treated like data types.
* Lambda expressions provide a shorthand syntax to write functions.
* You can pass function types into other functions.
* You can return a function type from another function.
* A lambda expression returns the value of the last expression.
* If a parameter label is omitted in a lambda expression with a single parameter, it's referred to with the `it` identifier.
* Lambdas can be written inline without a variable name.
* If a function's last parameter is a function type, you can use trailing lambda syntax to move the lambda expression after the last parenthesis when you call a function.
* Higher-order functions are functions that take other functions as parameters or return a function.
* The `repeat()` function is a higher-order function that works similarly to a `for` loop.
## Add a button to an app
* Define composable functions.
* Create layouts with Compositions.
* Create a button with the `Button` composable.
* Import `drawable` resources.
* Display an image with the `Image` composable.
* Make an interactive UI with composables.
* Use the `remember` composable to store objects in a Composition to memory.
* Refresh the UI with the `mutableStateOf()` function to make an observable.

* Attach the debugger to an app.
* Launch an app with the debugger already attached.
* Gain familiarity with the debugger pane.
* Set a breakpoint.
* Resume the program from the debugger.
* Use the `Step Into` button.
* Use the `Step Over` button.
* Use the `Step Out` button.
* Inspect variables with the debugger.
## Interacting with UI and state
### Intro to state in Compose
* State in an app is any value that can change over time.
* The Composition is a description of the UI built by Compose when it executes composables.Compose apps call composable functions to transform data into UI.
* Initial composition is a creation of the UI by Compose when it executes composable functions the first time.
* Recomposition is the process of running the same composables again to update the tree when their data changes.
* State hoisting is a pattern of moving state to its caller to make a component stateless.
### Write automated tests
* What automated tests are.
* Why automated tests are important.
* The difference between local tests and instrumentation tests
* Fundamental best practices for writing automated tests.
* Where to find and place local and instrumentation test classes in an Android project.
* How to create a test method.
* How to create local and instrumentation test classes.
* How to make assertions in local and instrumentation tests.
* How to use test rules.
* How to use `ComposeTestRule` to launch the app with a test.
* How to interact with composables in an instrumentation test.
* How to run tests.

# Android quizzes (lvl: Beginner)

## Unit 1:
### Introduction to Kotlin(quiz 1)

1. Which of the following variable declarations is valid?
  * `var hello: Int? = ""`
  * `String "hello" = hello`
  * 🟢 `val hello = "hello"` 🟢
  * `hello: String = "hello"`

2. It is considered best practice to declare a variable that will not change using `var` instead of `val`.
  * True
  * 🟢 False 🟢

3. Which of the following are valid ways to update a variable? (Choose as many answers as you see fit.)
  * 🟢 `total++` 🟢
  * `total - 1`
  * 🟢 `total--` 🟢
  * 🟢 `total = total + 1` 🟢

4. In Kotlin, comments can be single or multi-line and are ignored by the compiler.
  * 🟢 True 🟢
  * False

5. Which of the following is not a data type in Kotlin?
  * `String`
  * 🟢 `Decimal` 🟢
  * `Int`
  * `Boolean`

6. Float also represents a decimal, but is less precise than Double.
  * 🟢 True 🟢
  * False

7. In Kotlin, the entrypoint of a program is the ___.
  * `println()` statement
  * `val` variable
  * 🟢 `main()` function 🟢
  * `return` statement

8. Which of the following are true about function return values? (Choose as many answers as you see fit.)
  * 🟢 If a function does not specify a return type, the return type is `Unit`. 🟢
  * 🟢 A return value can be stored in a variable. 🟢
  * Functions with a return type of `Unit` must include a `return` statement.
  * 🟢 A return value's type must match the return type of a function. 🟢

9. Which of the following are true about functions? (Choose as many answers as you see fit.)
  * 🟢 Functions can take parameters, or variables as inputs. 🟢
  * Function parameters are required to have default arguments.
  * 🟢 When calling a function with parameters, the values passed in are called arguments. 🟢
  * 🟢 Breaking up your code into separate functions makes your code easier to maintain. 🟢

10. With named arguments, you can change the order in which you pass arguments into a function.
  * 🟢 True 🟢
  * False

### Setup Android Studio(quiz 2)

1. What does IDE stand for?
  * 🟢 Integrated Development Environment 🟢
  * Independent Design Environment
  * Ideal Developer Environment
  * Intelligent Design Environment

2. Which of the following are advantages of using Android Studio? (Choose as many answers as you see fit.)
  * 🟢 It can help prevent typos and other mistakes in your code. 🟢
  * 🟢 It comes with a virtual device called an emulator that can run your app. 🟢
  * 🟢 It can show you a real-time preview of how your app will look on-screen while you code. 🟢
  * It can automatically translate your app into other languages.

3. What is the purpose of using a virtual device, or emulator, in Android Studio?
  * To show a variety of error messages to users
  * To experiment with app code safely
  * 🟢 To test your app on a device without having that physical device 🟢
  * To see what your app looks like in a web browser

4. In Android Studio, what is a project template good for? (Choose as many answers as you see fit.)
  * It causes Android Studio to download files faster.
  * 🟢 It makes getting started on building a new app faster. 🟢
  * 🟢 It provides a structure that follows best practices. 🟢
  * It is the only way to build apps that can be previewed in Android Studio.
  * 🟢 It makes building a new app less error-prone by pre-populating the project with some app code. 🟢

5. How do you create a new project in Android Studio?
  * A. Log out of Android Studio, and navigate to your project folder to find instructions.
  * B. If you have a project already open, select File > New > New Project from the Android Studio menu.
  * C. In the “Welcome to Android Studio” window, click “Start a new Android Studio project.”
  * D. Create a new file on your computer, and title it “New Android Studio Project."
  * 🟢 Both B and C are ways to create a new project in Android Studio. 🟢
  * None of the above

6. ___ is a function that is used to define a layout in your app using Composable functions.
  * `ComponentActivity()`
  * `onCreate()`
  * `DefaultPreview()`
  * 🟢 `setContent()` 🟢

7. A Compose function requires the `@Composable` annotation.
  * 🟢 True 🟢
  * False

8. A ___ is a Composable that has a background color and can contain other Composables.
  * Color
  * Container
  * 🟢 Surface 🟢
  * Box

9. Padding is an example of a ___
  * Property
  * Composable
  * Attribute
  * 🟢 Modifier 🟢

10. Which of the following is false about Compose?
  * The Empty Compose Activity template is used to create a simple app.
  * Layouts can be viewed in the Preview window, without actually running your app.
  * 🟢 All elements and themes in a Compose app are contained in a Surface. 🟢
  * Themes, such as `GreetingCardTheme` allow you to style Composables.

### Build a basic layout(quiz 3)

1. What is Jetpack Compose?
  - Toolkit to design libraries
  - Database Interface
  - Plugin to build APK
  - 🟢 A Modern toolkit to develop Android UI 🟢

2. Composable functions are the basic building block of Compose.
  - True
  - 🟢 True 🟢
  - False

3. What annotation is used to annotate a Composable function?
  - `@Annotation`
  - `@ComposableFunction`
  - 🟢 `@Composable` 🟢
  - `@Preview`

4. The basic standard layout elements in Compose are: (Choose as many answers as you see fit.)
  - 🟢 Column 🟢
  - 🟢 Row 🟢
  - Text
  - 🟢 Box 🟢

5. What is the tool window for importing, creating, managing, and using resources in your app?
  - Application Manager
  - 🟢 Resource Manager 🟢
  - Resource Tool
  - Layout Manager

6. Which class is an automatically generated class by Android that contains the IDs of all resources in the project?
  - The `Android` class
  - The `Resource` class
  - 🟢 The `R` Class 🟢
  - The `ResourceID` class

7. Which function is used to load a drawable image resource?
  - The `stringResource()` function
  - 🟢 The `painterResource()` function 🟢
  - The `ImageResource()` function
  - The `loadResource()` function

8. What is the function parameter used to add accessibility text, used by talkback?
  - `accessibilityText`
  - `contentText`
  - `accessibilityDescription`
  - 🟢 `contentDescription` 🟢

9. The Box layout stacks the UI elements on top of one another.
  - 🟢 True 🟢
  - False

10. What parameter is used to align the child element to the beginning of the parent?
  - `Alignment.End`
  - `Alignment.Begin`
  - 🟢 `Alignment.Start` 🟢
  - `Alignment.Top`

## Unit 2:
### Kotlin fundamentals(quiz 1)
1. The following code will print "Divisible by 5" if number is equal to 25.
```
if (number % 10 == 0) {
  println("Divisible by 10")
} else if (number == 5) {
  println("Divisible by 5")
}
```
  - True
  - 🟢 False 🟢

2. Which of the following conditions are satisfied when x = 5? (Choose as many answers as you see fit.)
  - 🟢 x == 5 🟢
  - 🟢 x in 1..5 🟢
  - 🟢 x is Int 🟢
  - x % 5

3. Which is not a basic concept of object-oriented programming?
  - Abstraction
  - 🟢 Readability 🟢
  - Inheritance
  - Polymorphism

4. Which are the four visibility modifiers in Kotlin?
  - public, private, protected, abstract
  - static, override, internal, external
  - 🟢 private, protected, public, internal 🟢
  - public, protected, static, internal

5. The ___ keyword is used to call a method from the parent class.
  - this
  - 🟢 super 🟢
  - parent
  - self

6. A(n) ___ defines properties or methods that a class needs to implement.
  - Delegate
  - Generic type
  - 🟢 Interface 🟢
  - Subclass

7. Which of the following is best represented by a nullable type?
  - The number of followers (0 or more) in a social media app.
  - 🟢 An optional profile picture. 🟢
  - A username that must be at least one character.
  - A unique ID given to every user.

8. The ___ operator allows you to call a method only if the object is non-null.
  - `.`
  - `!!`
  - `?:`
  - 🟢 `?.` 🟢

9. Which is not true of functions in Kotlin?
  - 🟢 A function can be changed to another data type, and vice versa. 🟢
  - A function can be returned from another function.
  - A function can take another function as a parameter.
  - A function has a data type, such as (Int) -> Unit.

10. A function literal is another name for a ___.
  - Function type
  - 🟢 Lambda expression 🟢
  - Function reference
  - Trailing lambda

### Add a button to an app(quiz 2)
1. Use a ___ Composable to display an image
  - Button
  - Text
  - 🟢 Image 🟢
  - Icon

2. `Alignment.Center` centers UI components both horizontally and vertically.
  - 🟢 True 🟢
  - False

3. Composable functions can store an object in memory using the ___ composable
  - 🟢 remember 🟢
  - Column
  - Modifier
  - @Composable

4. The debugger allows you to inspect variables when code execution has been suspended.
  - 🟢 True 🟢
  - False

5. By using ___ values in a composable function, variables can be made into observables that schedule a recomposition when their value is changed.
  - remember
  - Modifier
  - @Composable
  - 🟢 mutableStateOf 🟢

6. The ___ composable places its children in a vertical sequence.
  - Row
  - Box
  - 🟢 Column 🟢
  - Modifier

7. The ___ debugger feature allows you to navigate back up the call stack.
  - Step over
  - 🟢 Step out 🟢
  - Step into
  - Resume program
### Interacting with UI and state(quiz 3)
1. Jetpack Compose runs your composables for the first time, during ___ it will keep track of the composables that you call to describe your UI.
 - 🟢 Initial composition 🟢
 - Recomposition
 - State change
 - App termination

2. The only way to modify a Composition is through recomposition.
 - 🟢 True 🟢
 - False

3. ___ is when Jetpack Compose re-executes the composables that may have changed in response to data changes.
 - Initial composition
 - 🟢 Recomposition 🟢
 - State change
 - App termination

4. ___ in an application is any value that can change over time.
 - 🟢 State 🟢
 - value
 - valueChange
 - StateValue

5. ___ is a pattern of moving state up to make a component stateless.
 - State change
 - 🟢 State hoisting 🟢
 - Hoist composition
 - Recomposition

6. Which `KeyboardAction` property is used to move the focus to the next composable?
 - `onDone`
 - 🟢 `onNext` 🟢
 - `onGo`
 - `onSend`

7. Which of the following Kotlin functions is used to round up a Double or Float?
 - `kotlin.math.ceilUp()`
 - 🟢 `kotlin.math.ceil()` 🟢
 - `kotlin.math.roundDown()`
 - `kotlin.math.roundUp()`

8. Layout Inspector is a tool in Jetpack Compose that allows you to inspect a Compose layout inside a running app in an emulator or physical device.
 - 🟢 True 🟢
 - False

9. UI tests are stored in the ___ directory.
 - main
 - 🟢 androidTest 🟢
 - test
 - res

10. Local tests and UI tests should be annotated with the ___ annotation.
 - `@VisibleForTesting`
 - `@Preview`
 - 🟢 `@Test` 🟢
 - `@Composable`
