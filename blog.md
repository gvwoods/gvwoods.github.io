
<ul>
  {% for post in site.posts %}
    <li>
      <a href="http://georgevwoods.com{{ post.url }}">{{ post.title }}</a> 
      <ul>
        <li>{{ post }}</li>
      </ul>
    </li>
  {% endfor %}
</ul>
