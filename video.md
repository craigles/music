<div style="text-align: center;">
  <h1>video</h1>
</div>

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
