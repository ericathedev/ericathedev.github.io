---
layout: page
---

<h2>About Me</h2>
🚧 👷🏻‍♀️ This part of the site is still under construction - check back later for more info! 👷🏻‍♀️ 🚧

<h2>Blog</h2>
My blog posts can be found at [this url]({% link blog/index.markdown %}). Here's a list of some topics I write about if you want to learn more.

{% capture temptags %}
  {% for tag in site.tags %}
    {{ tag[1].size | plus: 1000 }}#{{ tag[0] }}#{{ tag[1].size }}
  {% endfor %}
{% endcapture %}
{% assign sortedtemptags = temptags | split:' ' | sort | reverse %}
{% for temptag in sortedtemptags %}
  {% assign tagitems = temptag | split: '#' %}
  {% capture tagname %}{{ tagitems[1] }}{% endcapture %}
  <a href="/tag/{{ tagname }}"><code class="highligher-rouge"><nobr>{{ tagname }}</nobr></code></a>
{% endfor %}