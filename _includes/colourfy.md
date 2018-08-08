{% for c in include.text %}
  {% include random.md min=0 max=255 %}
  <span style="color: rgb(100, 100, 100)">{{c}}</span>
{% endfor %}
