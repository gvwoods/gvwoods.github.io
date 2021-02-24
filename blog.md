
<ul>
  {% for post in site.posts %}
    <li>
      <a href="https://georgevwoods.com{{ post.url }}">{{ post.title }}</a> 
      <ul>
        <li>{{ post.categories }}</li>
      </ul>
    </li>
  {% endfor %}
</ul>
