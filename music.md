# music

{% include audioList.html items=site.data.music %}
<script type="text/javascript">
  document.querySelectorAll('audio').forEach(item => {
    item.addEventListener('ended',function(e) {
        var allAudios = document.getElementsByTagName('audio');
        var index = allAudios.indexOf(document.getElementById(e.currentTarget.id));
        var next = allAudios[index+1];
        if (next) {
          next.play();
        }
    });
  });
</script>
