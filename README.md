# music
{% assign items = site.data.recordings | sort: 'date' %}
<table>
{% for r in items reversed %}
    <tr>
        <td>{{r.date}}</td>
        <td>
            {{r.title}}
        </td>
        <td>
            <audio src="{{site.url}}/recordings/{{r.path}}" controls preload="none" loop />
        </td>
    </tr>
{% endfor %}
</table>
