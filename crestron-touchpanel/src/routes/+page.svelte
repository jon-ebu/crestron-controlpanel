<script>
  import VideoControls from "$lib/VideoControls.svelte";
  import Footer from "$lib/Footer.svelte"; // Verify this path and ensure Footer.svelte is correctly exported
  import "../app.css"; // Ensure this path is correct

  let inputSources = [
    {
      selectedLabel: "WALL HDMI",
      unselectedLabel: "WALL HDMI",
      selectedColor: "black",
      unselectedColor: "gray",
    },
    {
      selectedLabel: "FLOOR HDMI",
      unselectedLabel: "FLOOR HDMI",
      selectedColor: "black",
      unselectedColor: "gray",
    },
  ];

</script>

<div>
  
<div id="scaling-container">
  <div id="page-container">
    <!-- Main Screen Section -->
    <VideoControls title="MAIN SCREEN" inputSources={inputSources} />
    <Footer />
  </div>
</div>
</div>

<style>

</style>

