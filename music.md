# music

{% include audioList.html items=site.data.music %}
<script type="text/javascript">
  document.querySelector('audio').addEventListener('ended',function(e) {
      document.getElementById(e.currentTarget.id).play();
    });
</script>
