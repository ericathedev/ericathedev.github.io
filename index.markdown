---
layout: page
---

<img style="float: left; border-radius: 10px; margin-right: 50px;" src="/assets/erica_tanti.jpg">

<h2>About Me</h2>
Hi I'm Erica Tanti and I'm a a Software Engineer ( _ahem, Developer?_ ) from Malta! 

Welcome to `👩🏻‍💻Erica the Dev`, my little spot on the internet where I'll be sharing
by knowledge from my 9 years working in the software industry.

<br />
<br />

<h2>Blog</h2>
My blog posts can be found at [this url]({% link blog/index.markdown %}). Here's a list of topics I've written about to get you started.

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