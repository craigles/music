# recursor
{% assign items = site.data.recordings | sort: 'date' %}
<table>
{% for r in items reversed %}
    <tr>
        <td>{{r.date}}</td>
        <td>
            {{r.title}}
        </td>
        <td>
            <audio controls preload="none" loop>
                <source src="{{site.url}}/recordings/{{r.path}}" type="audio/mpeg">
            </audio>
        </td>
    </tr>
{% endfor %}
</table>
