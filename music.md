# music

{% include audioList.html items=site.data.music %}
<script type="text/javascript">
  document.querySelector('audio').addEventListener('ended',function(e) {
      var next = document.getElementById(parseInt(e.currentTarget.id) + 1);
      if (next) {
        next.play();
      }
    });
</script>
