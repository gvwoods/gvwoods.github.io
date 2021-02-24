
<ul>
  {% for post in site.posts %}
    <li>
      <a href="/gvwoods.github.io{{ post.url }}">{{ post.title }}</a> 
  <li>{{ post.categories }}</li>
    </li>
  {% endfor %}
</ul>
