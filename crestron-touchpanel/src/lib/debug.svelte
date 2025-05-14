<script>
    import { onMount } from "svelte";
  
    onMount(() => {
      const videoControlDivs = document.querySelectorAll(".video-controls");
      console.log("Number of divs with class 'video-controls':", videoControlDivs.length);
    });
  </script>
  