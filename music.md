# music

{% include audioList.html items=site.data.music %}
<script type="text/javascript">
  document.querySelectorAll('audio').forEach(item => {
    item.addEventListener('ended',function(e) {
        var next = document.getElementById(parseInt(e.currentTarget.id) + 1);
        if (next) {
          next.play();
        }
    });
    item.addEventListener('play',function(e) {
        var allOtherAudios = document.querySelectorAll("audio:not([id='" + parseInt(e.currentTarget.id) + "']");
        allOtherAudios.forEach(a => {
          a.pause();
        });
  
        e.currentTarget.parentElement.parentElement.classList.add("playing");
    });
    
    item.addEventListener('pause',function(e) {
        e.currentTarget.parentElement.parentElement.classList.remove("playing");
    });
  });
</script>
