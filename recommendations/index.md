---
layout: page
title: "Recommendations Received"
modified: 2018-01-05
excerpt: "Recommendations I have received"
image:
  feature: 
  credit: 
  creditlink:
---

{% include _toc.html %}



### Paragraph Indentation

By default the margin below paragraphs has been removed and indent added to each. This is an intentional design decision to mimic the look of type set in a printed book or manuscript.

<figure>
  <img src="{{ site.url }}/images/paragraph-indent.png" alt="screen shot of paragraphs with default indent style set">
  <figcaption>Example of the default paragraph style (indented first line and bottom margin removed).</figcaption>
</figure>

To disable the indents and add spacing between paragraphs change the following line in `_sass/variables.scss` from `true !default` to `false` like so.

{% highlight css %}
$paragraph-indent: false;
{% endhighlight %}

<figure>
  <img src="{{ site.url }}/images/paragraph-no-indent.png" alt="screen shot of paragraphs with indent style disabled">
  <figcaption>Example of paragraphs with $paragraph-indent disabled.</figcaption>
</figure>

### Videos

Video embeds are responsive and scale with the width of the main content block with the help of [FitVids](http://fitvidsjs.com/).

Not sure if this only effects Kramdown or if it's an issue with Markdown in general. But adding YouTube video embeds causes errors when building your Jekyll site. To fix add a space between the `<iframe>` tags and remove `allowfullscreen`. Example below:

{% highlight html %}
<iframe width="560" height="315" src="http://www.youtube.com/embed/PWf4WUoMXwg" frameborder="0"> </iframe>
{% endhighlight %}

