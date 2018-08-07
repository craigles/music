# music
{% assign itemsByDate = site.data.music | sort: 'date' | group_by: 'date' %}

<table>
    {% for rGroup in itemsByDate %}
        {% for r in rGroup.items %}
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
