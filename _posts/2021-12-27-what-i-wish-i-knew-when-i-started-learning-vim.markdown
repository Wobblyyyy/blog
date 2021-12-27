---
layout: post
title:  "What I wish I knew when I started learning Vim"
date:   2021-12-27 18:05:43 -0500
categories: java
---
`vim` is a hugely influential text editor developed in the 1990's by Bram
Moolenaar. Unlike most modern text editors, there was no way to use a mouse.
Everything was done via keyboard shortcuts. This means two things: firstly,
you'll be able to navigate more quickly, as you won't ever have to move your
hand to the mouse. Secondly, you have to memorize a ton of shortcuts in order
to make even basic use of the text editor. Such an archaic editor still enjoys
widespread use in the software development community because it allows them to
navigate files much more easily. 

* TOC
{:toc}

# Unbind your arrow keys!
This one is pretty important. `vim`'s default mode of navigation is via
the `h`, `j`, 'k', and 'l' commands.
- `h` - move the cursor to the left
- 'j' - move the cursor downwards
- 'k' - move the cursor upwards
- `l` - move the cursor rightwards

## Why?
Unbinding your arrow keys may sound counter-intuitive at first - why would I
want to disable part of my keyboard? I assure you the benefit is worth it. If
you don't unbind your arrow keys, you'll continue using them all the time,
meaning you won't start to pick up on `vim` and all of its capabilities.

## How?
You'll need to execute some commands in order to unbind your arrow keys. If
you don't know what a `.vimrc` file is, I'd suggest you look it up, as it's
an important concept. You want to modify your `.vimrc` file, appending the
following lines:
{% highlight vimscript %}
noremap <Up> <Nop>
noremap <Down> <Nop>
noremap <Left> <Nop>
noremap <Right> <Nop>
{% endhighlight %}
This will disable the usage of the arrow keys. If you're using it correctly,
you'll never need to use your arrow keys anyways - they'd just slow you down.
