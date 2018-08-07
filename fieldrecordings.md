# Field Recordings
{% assign items = site.data.fieldRecordings | sort: 'date' %}
<table>
{% for r in items reversed %}
    <tr>
        <td>{{r.date}}</td>
        <td>
            {{r.title}}
        </td>
        <td>
            <audio src="{{site.url}}/recordings/{{r.path}}" controls preload="none" />
        </td>
    </tr>
{% endfor %}
</table>
