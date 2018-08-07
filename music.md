# music
{% assign itemsByDate = site.data.music | group_by: 'date' | sort: 'date' %}

<table>
    {% for rDate in itemsByDate %}
        {% assign items = rDate.items | sort: 'title' %}
        {% for r in items %}
            <tr>
                <td>{{r.date}}</td>
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
