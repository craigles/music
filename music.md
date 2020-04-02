# music

{% include audioList.html items=site.data.music %}
<script type="text/javascript">
  music.addEventListener('ended',function(e) {
      document.getElementById(e.currentTarget.id).play();
    });
</script>
