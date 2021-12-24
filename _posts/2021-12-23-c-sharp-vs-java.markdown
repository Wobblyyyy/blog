---
layout: post
title:  "C# and Java compared - which is better?"
date:   2021-12-23 19:03:59 -0500
categories: java
---
Java and C# are the two largest VM-based object-oriented programming languages.
Created originally by James Gosling in the 90's at Sun Microsystems, Java was
a revolutionary language - utilizing the Java Virtual Machine, code could be
written once and ran anywhere. C# was designed by Anders Hejlsberg and was 
created in 2000 at Microsoft. Both languages share several traits - most
importantly, they're languages that are compiled to a sort of intermediate
language, which is then executed by a runtime environment. Additionally, they
have very similar syntax, roughly derived from that of C++.

# Which one is better?
Here - I'll spoil it for you - C# is better. If you don't have the energy,
time, or motivation to read through the entire article: in summary, C# is
better than Java because it was created years later after many users had the
chance to find Java's faults. Adding functionality and improving syntax were
two of the accomplishments of the introduction of C#. Although Java has a
larger open-source ecosystem and the JVM is generally more widely supported
than the CLR, C# is a significantly more developer-friendly language with
some neat features that give it an advantage over Java.

## Performance
Performance is a major factor when considering which language you should use.
Given the performance of modern computers, performance often isn't (and
shouldn't be) the deciding factor. I'd like to say that if you're trying to
decide between Java and C#, they have very similar (nearly identical)
performance, and you should consider other advantages and disadvantages of
each of the languages unless you have a reason not to.

## Code style

## Language features
Alright. This is where C# really shines, and where Java... does not shine.

### Getters and setters vs Records
Anyone who's written a line of Java in their life can tell you what a getter
and setter method are.

#### C#'s "Properties"
{% highlight c# %}
public class ExampleClass
{
    public string ExampleString { get; set; }
    public int ExampleInt { get; set; }
    public bool ExampleBool { get; set; }
}
{% endhighlight %}
Writing classes in Java that simply contain a bunch of values and getter and
setter values for those values is a tedious process that leads to simple Java
programs requiring dozens of lines of boilerplate code. In C#, with getter
and setter design they've implemented, it's significantly easier, and can be
done significantly more effectively. Check out the official documentation
page for [Properties][properties] to learn more. Those properties can be
used as follows:
{% highlight c# %}
// creating a new instance of ExampleClass
ExampleClass example = new ExampleClass();

// creating a new instance of ExampleClass, with values
example = new ExampleClass
{
    ExampleString = "example string value",
    ExampleInt = 100,
    ExampleBool = true
};

// accessing properties of ExampleClass
string exampleString = example.ExampleString;
int exampleInt = example.ExampleInt;
bool exampleBool = example.ExampleBool;

// setting properties of ExampleClass
example.ExampleString = "new example";
example.ExampleInt = 1_000;
example.ExampleBool = false;
{% endhighlight %}
Properties are a neat feature of C# that I would encourage you to do some
more reading into - I don't have the energy to type out all the info
I'd like to here, but [Microsoft's docs][properties] does it for me.

#### Java's "Records"
Records were introduced in 2021 with the release of Java 16. They're pretty
nice - they make it easy to make types that store values. Here's an example:
{% highlight java %}
public record ExampleRecord(String exampleString,
                            int exampleInt,
                            boolean exampleBoolean) {
}
{% endhighlight %}
This automatically generates a constructor, as well as some methods which can
be used to access these properties.
{% highlight java %}
// constructor
ExampleRecord exampleRecord = new ExampleRecord(
    "example string value",
    100,
    true
);

// accessing the properties
String exampleString = exampleRecord.exampleString();
int exampleInt = exampleRecord.exampleInt();
boolean exampleBoolean = exampleRecord.exampleBoolean();
{% endhighlight %}

#### Java's "record classes"
Unfortunately, most of the world doesn't use Java 16, meaning records...
well, they're not yet supported. As a sort of workaround, Java developers
have come up with a design pattern something like this.
{% highlight java %}
public class ExampleRecordClass {
    private String exampleString;
    private int exampleInt;
    private bool exampleBool;
    
    public ExampleRecordClass() {

    }

    public void setExampleString(String exampleString) {
        this.exampleString = exampleString;
    }

    public String getExampleString() {
        return exampleString;
    }

    public void setExampleInt(int exampleInt) {
        this.exampleInt = exampleInt;
    }

    public int getExampleInt() {
        return exampleInt;
    }

    public void setExampleBoolean(boolean exampleBoolean) {
        this.exampleBoolean = exampleBoolean;
    }

    public boolean getExampleBoolean() {
        return exampleBoolean;
    }
}
{% endhighlight %}

[properties]: https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/using-properties