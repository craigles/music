<h1 style="text-align: center;">video</h1>

{% assign items = site.data.video | sort: 'date' %}
<table>
{% for r in items reversed %}
    <tr>
        <td>{{r.date}}</td>
        <td>
            {{r.title}}
        </td>
    </tr>
    <tr>
        <td>
            <video src="{{site.url}}/recordings/{{r.path}}" controls preload="none" />
        </td>
    </tr>
{% endfor %}
</table>
