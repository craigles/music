# music
{% assign itemsByDate = site.data.music | group_by: 'date' %}
{% assign itemsSorted = itemsByDate reversed | sort: 'title' %}
<table>
{% for rDate in itemsSorted %}
    {% assign items = rDate.items | sort: "title" %}
    {% for r in items %}
        <tr>
            <td>{{rDate.date}}</td>
            <td>
                {{r.title}}
            </td>
            <td>
                <audio src="{{site.url}}/recordings/{{r.path}}" controls controlsList="nodownload" preload="none" />
            </td>
        </tr>
    {% endfor %}
{% endfor %}
</table>
