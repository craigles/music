# music
{% assign itemsByDate = site.data.music | sort: 'date' | group_by: 'date' | reverse %}
{% assign totalLength = 0 %}
<table>
    {% for rGroup in itemsByDate %}
        {% assign rGroupItems = rGroup.items | sort: 'title' %}
        {% for r in rGroupItems %}
            {% assign lengthComponents = r.length | split: ':' %}
            {% assign totalLength = totalLength | plus: lengthComponents[1] %}
            <tr>
                <td>{{r.date}}</td>
                <td>
                    {{r.title}}
                </td>
                <td>
                    {{r.length}}
                </td>
                <td>
                    <audio src="{{site.url}}/recordings/{{r.path}}" controls controlsList="nodownload" preload="none" />
                </td>
            </tr>
        {% endfor %}
    {% endfor %}
</table>

{{totalLength}}
