# music
{% assign itemsByDate = site.data.music | sort: 'date' | group_by: 'date' | reverse %}
{% assign totalMinutes = 0 %}
{% assign totalHours = 0 %}

<table>
    {% for rGroup in itemsByDate %}
        {% assign rGroupItems = rGroup.items | sort: 'title' %}
        {% for r in rGroupItems %}
            {% assign lengthComponents = r.length | split: ':' %}
            {% assign totalMinutes = totalMinutes | plus: lengthComponents[1] %}
            {% assign totalHours = totalHours | plus: lengthComponents[0] %}
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
{% assign totalMinutesHours = totalMinutes | divided_by: 60 %}
{% assign totalHours = totalHours | plus: totalMinutesHours %}

{% assign totalMinutes = totalMinutes | modulo: 60 %}
{{totalHours}}
{{totalMinutes}}
