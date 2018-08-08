{% assign chars = include.text | split: '' %}
{% for c in chars %}
  <span style="
  color: rgb(
  {% include random.md min=0 max=150 %}, 
  {% include random.md min=0 max=150 %}, 
  {% include random.md min=0 max=150 %})">
  {{c}}
  </span>
{% endfor %}
