---
layout: page
title: Carnot-Jekyll, Style Guide
---

> Life is nature's solution to the problem of preserving information despite the second law of thermodynamics.
  *(Howard L. Resnikoff)*

This is my first time designing anything similar to a webpage. I've tried to make sure my aesthetic wishes are fulfilled with my design. So, just to make sure everything is well followed, I've this style guide. Enjoy!

# Lists

There are two types of lists: unordered and ordered. So, I'll give you a mixed list to see both types of lists in action.

- Asimov's Three Laws:
    1. A robot may not injure a human being or, through inaction, allow a human being to come to harm
    2. A robot must obey the orders give it by human beings except where such orders would conflict with the First Law.
    3. A robot must protect its own existence as long as such protection does not conflic with the First or Second Laws.
- Asimov's laws of robotics are analogues of the Laws that are implicit in design of almost all tools, robotic or not robotic.

# Code

Code snippets inline look like `class style()` and `value=5`. While multi-line code blocks in python look like:

{% highlight python %}
class vignesh:
    def __init__(self):
        self.str = "what the fuck?"

    def do_something(self, here):
        """Docstrings are awesome"""
        Have to do something here.

    @staticmethod
    def stacy(here, there):
        print(here, there)
{% endhighlight %}

For HTML, the block changes to:

{% highlight html %}
<div class="link-posts">
    <h2>
        <a href="{{ site.url }}{{ post.url }}" title="{{ post.title }}">
        </a>
    </h2>
</div> 
{% endhighlight %}

# Images

![Fronds]({{ site.url }}/assets/images/fronds.jpeg)

