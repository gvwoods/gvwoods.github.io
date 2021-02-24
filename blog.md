
<ul>
  {% for post in site.posts %}
    <li>
      <a href="/gvwoods.github.io/blog/{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
