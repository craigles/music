# recursor!

<table>
{% for r in site.data.recordings %}
    <tr>
        <td>{{r.date}}</td>
        <td><a href="{{site.url}}/{{r.path}}">{{r.title}}</a></td>
    </tr>
{% endfor %}
</table>
