---
layout: page
title: About
---

What is Conductor?
===
At its core, Conductor is just a wrapper for the Selenium WebDriver API.

Conductor...

1. uses the concept of [fluent interfaces](http://en.wikipedia.org/wiki/Fluent_interface) to create very fluid, 
and easy to read/write tests.

2. *abstracts the tester from annoying implicit explicit waits*.  Conductor will wait at a pre-specified time to make sure
something has appeared, and is ready to be interacted with.

3. comes packaged with tons of validation methods that are commonly used with testing:
  * `validateText`
  * `validateTextNot`
  * `validateChecked`
  * `validateUnchecked`
  * `validatePresent`
  * `validateNotPresent`
  * `validateTextPresent`
  * `validateTextNotPresent`
  * `validateTrue`
  * `validateFalse`
  * ...

4. also comes bundled with all the actions you'll need:
  * `click()`
  * `setText()`
  * `check()`
  * `uncheck()`
  * `selectOptionByValue()`
  * `selectOptionByText()`
  * `navigateTo()`
  * `isPresent()`
  * `getText()`
  * `hoverOver()`
  * `getAttribute()`
  * `goBack()`
  * `switchToWindow()`
  * `waitForWindow()`
  * ...

5. reveals the base `driver` object, so you can, if you so choose, still use the methods provided from `driver`  (`driver.findElement()`, etc)

6. is extremely easy for new QA engineers to use.  Little programming knowledge is required to understand the concept behind
Conductor.

Why `Conductor'?
===
Much like any other software package out there, Conductor is a just a play on words.

The concept stems from the concept of a train conductor.  A train conductor is the one that is responsible for the operational
duties upon a train. Much like a train, the Conductor selenium framework is responsible for the operational duties of your
automated testing.

You may have noticed that the base class that you extend from, is called `Locomotive`.  This also is, of course, another play
on words.  In the world of Object Oriented Programming, a class can extend and inherit methods, properties, etc from a super class.
*Much like a train...* your tests will extend from the Locomotive (the front engine of a train) and the Locomotive will pull you
forward.

Also, much like *WebDriver* drives the web, *Conductor* drives your tests.

Why are you still reading?
===
[Get started](/get-started)!
