---
layout: page
title: Get Started
---

Get Started using Conductor
===

The easiest way to get up and running with Conductor, is by using Maven.

In your `pom.xml` file, just add:

{% highlight xml %}
<dependency>
  <groupId>io.ddavison</groupId>
  <artifactId>conductor</artifactId>
  <version>{{site.conductor.version}}</version>
</dependency>
{% endhighlight %}

Writing your first test class
===
Create a new Java class once Maven is all setup, and extend the class from  `Locomotive`, as well as provide
the `Config` annotation.

{% highlight java %}
@Config(
    browser = Browser.CHROME,
    url     = "http://your-app-url"
)
public class MyTest extends Locomotive {
    @Test 
    public void myTest() {
        // here we will already be at http://your-app-url, so start testing!
        click("#someId") // a css selector
        .click(By.xpath("you can also use a By locator strategy"));
    }
}
{% endhighlight %}

Preparing your own test framework
===
At it's heart, Conductor is meant to guide your tests, not necessarily your testing strategy.  It would be a good idea
to eventually create your own framework, which wraps Conductor.

Here is an example:

{% highlight java %}
@Config(
    browser = Browser.CHROME,
    url     = "http://your-app-url"
)
public class SuperClass extends Locomotive {}

// Now you can create your own test suite, all already configured to use the configuration specified in the super class.

public class MyTestSuit extends SuperClass {
    @Test
    public void testSomething() {
        ...
    }

    @Test
    public void testSomethingElse() {
        ...
    }
}
{% endhighlight %}

Connect conductor to a Selenium Grid
===
You can specify a grid URL inside of the `@Config` annotation passed to your superclass / subclass

{%highlight java%}
@Config(
    browser = Browser.CHROME,
    url     = "http://your-app-url",
    hub     = "http://your-hub-url:4444/wd/hub"
)
...
{%endhighlight%}

Using Conductor with TestNG
===
Conductor, out of the box uses jUnit as its test framework.  You can enable TestNG by providing your own before/after
methods, and calling the jUnit after method.

{%highlight java%}
public class TestNGBaseTest extends Locomotive {
    public TestNGBaseTest() {
        super();
    }

    @Before // testng before
    public void before() {}

    @After // testng after
    public void after() {
        teardown();
    }
}

public class MyTest extends TestNGBaseTest {
    // ...
}
{%endhighlight%}
