# Dependency Injections: How to Level Up Your Code

What if I told you that there was a software development concept that could dramatically improve your code's flexibility, maintainability, and testability?

Sounds too good to be true, you say? Well then you have likely never heard of Dependency Injection.

Today, we will unravel the basics of Dependency Injection and why it could be the next tool to level up your code.

## Ok, I’m listening. But what even is Dependency Injection anyway?

A dependency is an object that relies on another object. Dependency Injection is a design pattern that promotes loose coupling between components in your application. It allows you to provide dependencies (usually objects) to a class rather than having the class create them itself. This approach enhances code reusability, testability, and maintainability.

## Now for a Demonstration:

For this example, we have a `Person` class that requires a `Name` object to be constructed. Without any knowledge of Dependency Injection, you might create a `Name` object inside the ‘Person’ class like this:

![image](https://github.com/skylarbsandler/Today-I-Learned/assets/95989203/b9d23e8e-aff6-4af8-ac6d-b7dd3320b54e)

While this will get the job done, it could cause headaches down the road. This approach tightly couples the `Person` and `Name` classes. If you ever wanted to change `Name` to a different implementation, you would have to change both classes. This may seem like no big deal with only two classes, but imagine if 100 other classes used the `Name` object. Additionally, our current code makes it difficult to create a mock of `Name` for testing.

## Enter Dependency Injection:

To implement Dependency Injection, we can modify the `Person` class to accept a `Name` object through its constructor:

![image](https://github.com/skylarbsandler/Today-I-Learned/assets/95989203/688e5a00-4514-4372-867c-b4b836739430)

Now, when creating a `Person` object, you can inject a `Name` object:

![image](https://github.com/skylarbsandler/Today-I-Learned/assets/95989203/10dbfa70-019a-4bcc-b248-679cca5b9f2d)

This decouples the `Person` class from the `Name` class, making our code more flexible and maintainable.

This is just one of many, many applications, but as you can see, Dependency Injection has a lot of benefits. However, as with most software concepts, it does not come without some drawbacks:
- It can require more upfront effort to configure and manage dependency which can require extra code and configuration files.
- Added complexity; can make code difficult to trace because it separates behavior from construction
- Increase performance overhead as dependency injections need to create and inject the dependencies at runtime

While these risks are important to keep in mind, when used correctly, Dependency Injection adds a lot to your code in terms of flexibility, testability, and maintainability. 

If you want to dive in deeper, here are some Dependency Injection resources I really enjoyed:
- [Dependency Injection in C# (2023)](https://www.c-sharpcorner.com/UploadFile/85ed7a/dependency-injection-in-C-Sharp/)
- [Dependency Injection Design Pattern in C#](https://dotnettutorials.net/lesson/dependency-injection-design-pattern-csharp/#google_vignette)
- [Dependency Injection for Absolute Beginners with C# and .NET](https://www.youtube.com/watch?v=tTJetZj3vg0)
