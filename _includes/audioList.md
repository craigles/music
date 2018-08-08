{% assign itemsByDate = include.items | sort: 'date' | group_by: 'date' | reverse %}
{% assign totalMinutes = 0 %}
{% assign totalHours = 0 %}

<table>
    <tbody>
        {% for rGroup in itemsByDate %}
            {% assign rGroupItems = rGroup.items | sort: 'title' %}
            {% for r in rGroupItems %}
                {% assign lengthComponents = r.length | split: ':' %}
                {% assign totalMinutes = totalMinutes | plus: lengthComponents[1] %}
                {% assign totalHours = totalHours | plus: lengthComponents[0] %}
                <tr>
                    <td>{{r.date}}</td>
                    <td>
                        {{r.title}} {% include random.md max=100 %}
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
    </tbody>
    <tfoot>
        <tr>
            <td colspan="2"></td>
            <td>{% include totalTime.html minutes=totalMinutes hours=totalHours %}</td>
            <td></td>
        </tr>
    </tfoot>
</table>
