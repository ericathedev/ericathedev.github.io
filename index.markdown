---
layout: page
---
<style>
  .flex {
    display: flex;
  }

  .flex-row {
    flex-direction: row;
  }

  .flex-col {
    flex-direction: column;
  }

  .flex-wrap {
    flex-wrap: wrap;
  }

  .radius {
    border-radius: 10px
  }

  .mr {
    margin-right: 20px;
  }

  .mb {
    margin-bottom: 20px;
  }

  .flex-1 {
    flex: 1;
  }

  .align-items-center {
    align-items: center;
  }
</style>

<div class="flex flex-row flex-wrap align-items-center">
  <img style="min-width: 236px" class="mr mb radius flex" src="/assets/erica_tanti.jpg">
  <div class="flex flex-col flex-1" style="min-width: 400px">
    <h2>About Me</h2>
    <p>
      Hi I'm Erica Tanti and I'm a Software Engineer (<em>ahem, Developer?</em>) from Malta!
    </p>
    <p>
      Welcome to <code class="highligher-rouge">👩🏻‍💻Erica the Dev</code>, my little spot on the internet where I'll be sharing by knowledge from my 9 years working in the software industry.
    </p>
  </div>
</div>

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
    {%- for post in site.posts limit:3 -%}
    <li>
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      <span class="post-meta">{{ post.date | date_to_string }}</span>
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
