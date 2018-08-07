# video

{% assign items = site.data.video | sort: 'date' %}
<table>
{% for r in items reversed %}
    <tr>
        <td>{{r.date}}</td>
        <td>
            {{r.title}}
        </td>
        <td>
            <video src="{{site.url}}/recordings/{{r.path}}" controls preload="none" />
        </td>
    </tr>
{% endfor %}
</table>
