<ul class="posts">
    {% for post in site.posts %}
      <li>
        <a href="{{ post.url }}">{{ post.date | date: "%-d %B %Y" }} - {{ post.title }}</a>
        {{ post.excerpt }}
      </li>
    {% endfor %}
</ul>