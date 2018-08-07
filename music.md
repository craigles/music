# music
{% assign itemsByDate = site.data.music | sort: 'date' | group_by: 'date' | reverse %}

<table>
    {% for rGroup in itemsByDate %}
        {% assign rGroupItems = rGroup.items | sort: 'title' %}
        {% for r in rGroupItems %}
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
