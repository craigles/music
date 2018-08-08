{% assign chars = include.text | split: '' %}
{% for c in chars %}
  {% include random.md min=0 max=255 %}
  <span style="color: rgb(100, 100, 100)">{{c}}</span>
{% endfor %}
