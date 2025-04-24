<script>
  import VideoControls from "$lib/VideoControls.svelte";
  import Footer from "$lib/Footer.svelte"; // Verify this path and ensure Footer.svelte is correctly exported
  import "../app.css"; // Ensure this path is correct

  let inputSources = [
    {
      selectedLabel: "WALL HDMI",
      unselectedLabel: "WALL HDMI",
      selectedColor: "#FFA500",
      unselectedColor: "#ffc966",
    },
    {
      selectedLabel: "FLOOR HDMI",
      unselectedLabel: "FLOOR HDMI",
      selectedColor: "#304f30",
      unselectedColor: "#8FBC8F",
    },
    {
      selectedLabel: "AIR MEDIA",
      unselectedLabel: "AIR MEDIA",
      selectedColor: "#007FA3",
      unselectedColor: "#63ddff"
    },
  ];

</script>

<div>
  
<div id="scaling-container">
  <div id="page-container">
    <!-- Main Screen Section -->
    <VideoControls title="MAIN SCREEN" inputSources={inputSources} />
    <VideoControls title="SIDE SCREEN" inputSources={inputSources} />
  
    <Footer />
  </div>
</div>
</div>

<style>

</style>

