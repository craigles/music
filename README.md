# recursor
{% assign items = site.data.recordings | sort: 'date' %}
<table>
{% for r in items reversed %}
    <tr>
        <td>{{r.date}}</td>
        <td><a href="{{site.url}}/recordings/{{r.path}}?autoplay=1&loop=1&controls=0">{{r.title}}</a></td>
    </tr>
{% endfor %}
</table>
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
{% include open-embed.html %}
