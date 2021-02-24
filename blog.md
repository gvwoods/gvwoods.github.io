
<ul>
  {% for post in site.posts %}
    <li>
      <a href="/{{ post.url }}">{{ post.title }}</a> 
  <li>{{ post.categories }}</li>
    </li>
  {% endfor %}
</ul>
