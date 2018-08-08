{% assign chars = include.text | split: '' %}
{% for c in chars %}
  {% if c == ' ' %}
    &nbsp;
  {% else %}
    <a style="
    color: rgb(
    {% include random.md min=0 max=200 %}, 
    {% include random.md min=0 max=200 %}, 
    {% include random.md min=0 max=200 %})">
    {{c}}
    </a>
  {% endif %}
{% endfor %}
