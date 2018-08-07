# music
{% assign itemsByDate = site.data.music | group_by: 'date' | sort: 'date' %}
{% assign itemsByDateSorted = itemsByDate | sort: 'date' %}

<table>
    {% for rGroup in itemsByDateSorted %}
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
