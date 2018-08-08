{% assign chars = include.text | split: '' %}
{% for c in chars %}
  <span style="
  color: rgb(
  {% include random.md min=0 max=100 %}, 
  {% include random.md min=0 max=100 %}, 
  {% include random.md min=0 max=100 %})">
  {{c}}
  </span>
{% endfor %}
