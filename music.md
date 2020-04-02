# music

{% include audioList.html items=site.data.music %}
<script type="text/javascript">
  document.querySelectorAll('audio').forEach(item => {
    item.addEventListener('ended',function(e) {
        var allAudios = document.getElementsByTagName('audio');
        Array.from(allAudios).forEach((a, i) => {
          if (a.id === e.currentTarget.id) {
            var next = allAudios[i+1 + 1];
            if (next) {
              next.play();
            }
          }
        });
    });
  });
</script>
