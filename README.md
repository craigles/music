# recursor!
{% assign items = site.data.recordings | sort: 'date' %}
<table>
{% for r in items reversed %}
    <tr>
        <td>{{r.date}}</td>
        <td><a href="{{site.url}}/recordings/{{r.path}}">{{r.title}}</a></td>
    </tr>
{% endfor %}
</table>
