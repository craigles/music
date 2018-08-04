# recursor
<table>
{% assign recordings = site.data.recordings | sort: 'date' %}
{% for r in recordings %}
    <tr>
        <td>{{r.date}}</td>
        <td><a href="{{site.url}}{{r.path}}">{{r.title}}</a></td>
    </tr>
{% endfor %}
</table>
