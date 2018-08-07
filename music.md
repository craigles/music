# music
{% assign itemsByDate = site.data.music | group_by: 'date' | sort: 'title' %}

<table>
    {% for r in itemsByDate.items %}
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
</table>
