rec

{% for item in site.recordings %}
  <p><a href="{{ item.url }}">{{ item.title }}</a></p>
{% endfor %}
