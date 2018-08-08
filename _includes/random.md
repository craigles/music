{% assign random = site.time | date: "%s%N" | modulo: include.max %}
{{random}}
