---
layout: page
---

<img style="float: left; border-radius: 10px; margin-right: 50px;" src="/assets/erica_tanti.jpg">

<h2>About Me</h2>
Hi I'm Erica Tanti and I'm a Software Engineer ( _ahem, Developer?_ ) from Malta! 

Welcome to `👩🏻‍💻Erica the Dev`, my little spot on the internet where I'll be sharing
by knowledge from my 9 years working in the software industry.

<br />
<br />

<h2>Blog</h2>
My blog posts can be found at [this url]({% link blog/index.markdown %}). Here's a list of topics I've written about to get you started:

{% capture temptags %}
  {% for tag in site.tags %}
    {{ tag[1].size | plus: 1000 }}#{{ tag[0] }}#{{ tag[1].size }}
  {% endfor %}
{% endcapture %}
{% assign sortedtemptags = temptags | split:' ' | sort | reverse %}
<p>
    {% for temptag in sortedtemptags %}
        {% assign tagitems = temptag | split: '#' %}
        {% capture tagname %}{{ tagitems[1] }}{% endcapture %}
        <a href="/tag/{{ tagname }}"><code class="highligher-rouge"><nobr>{{ tagname }}</nobr></code></a>
    {% endfor %}
</p>

{%- if site.posts.size > 0 -%}
<br/>
  <h3>Latest Posts</h3>
  <ul class="post-list">
    {%- for post in site.posts | limit:3 -%}
    <li>
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      <span class="post-meta">{{ post.date | date: date_format }}</span>
      <h4>
        <a class="post-link" href="{{ post.url | relative_url }}">
          {{ post.title | escape }}
        </a>
      </h4>
      {{ post.excerpt }}
    </li>
    {%- endfor -%}
  </ul>

  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>
{%- endif -%}