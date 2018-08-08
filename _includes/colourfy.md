{% assign chars = include.text | split: '' %}
{% for c in chars %}
  <span style="
  color: rgb(
  {% include random.md min=0 max=200 %}, 
  {% include random.md min=0 max=200 %}, 
  {% include random.md min=0 max=200 %})">
  {{c}}
  </span>
{% endfor %}
