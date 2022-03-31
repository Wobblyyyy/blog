---
layout: post
title:  "Why Python is the root of all evil"
date:   2022-03-31 09:58:23 -0500
categories: python
---
Python is a high-level scripting language that first popped up in early 1991.
Designed by Guido van Rossum and maintained by the Python Software Foundation,
Python has exploded in popularity, due in part to its simple syntax,
ease-of-use, widespread availability, and high-level abstractions, making it
easy to write complex programs. Popular in fields like machine learning,
artificial intelligence, and computer vision, Python's high-level nature makes
it the de-facto language of anything involving a lot of data.

* TOC
{:toc}

# What Python is good at
A lot of things, actually. As much as I hate to admit it, Python is a popular
language for a reason. It's easy for inexperienced programmers to pick up, and
it's a great "first language." It has an intuitive syntax that abstracts away
many of the complexities of lower-level programming languages: memory
management and data structures, to name a few examples.

## It's popular. Extremely popular
![Graph of best programming languages to learn in 2022][best-langs-to-learn]

# Why Python is evil
Allow me to preface this by saying that the title of this section (and this
blog post) is (are) a bit hyperbolic in nature. Python isn't genuinely evil,
but I do believe that it's being overused, and I do believe that learning
Python first produces a syndrome best named "Python brain."

## It's slow
This is one of the most common critiques of Python, and for good reason.
Python, as a high-level language, is pretty slow. Scripting languages are
inherently slower than compiled languages. There are a couple of issues with
how Python is designed that further complicate these speed issues.

### Global interpreter lock
Python's "global interpreter lock" prevents multi-threading entirely. The idea
is that all components of a Python application must be executed on a single
thread. Certain libraries can circumvent this by using languages such as C to
handle multi-threading. But Python does not natively support the usage of
multiple threads. This proves to be a huge drawback when attempting to develop
applications that would need to utilize multiple threads in order to optimize
performance.

[Real Python][global-interpreter-lock] explains why the global
interpreter lock ("GIL") exists: in short, Python uses reference counting for
memory management. Using multiple threads complicates reference counting, so
the GIL exists as a workaround to that issue. If you're curious, you can go
ahead and read a bit more on [Real Python][global-interpreter-lock].

### Dynamic typing
This is more of an issue with scripting languages in general rather than just
Python, but it's certainly a component of what makes Python so slow.

## It's... too easy?
Alright. Allow me to explain myself here. Python is an incredibly easy language
to

{% highlight vimscript %}
noremap <Up> <Nop>
noremap <Down> <Nop>
noremap <Left> <Nop>
noremap <Right> <Nop>
{% endhighlight %}

[best-langs-to-learn]: https://d1rytvr7gmk1sx.cloudfront.net/wp-content/uploads/2021/12/most-in-demand-programming-languages-of-2022-codingnomads.jpg
[global-interpreter-lock]: https://realpython.com/python-gil/
