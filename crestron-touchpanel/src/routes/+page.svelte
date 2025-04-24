<script>
  import Button from "$lib/Button.svelte";
  import ButtonGroup from "$lib/ButtonGroup.svelte";
  import ControlGroup from "$lib/ControlGroup.svelte";
  import VideoControls from "$lib/VideoControls.svelte";
  import VolumeSlider from "$lib/VolumeSlider.svelte";
  import Footer from "$lib/Footer.svelte"; // Verify this path and ensure Footer.svelte is correctly exported
  import "../app.css"; // Ensure this path is correct

  let inputSources = [
    {
      selectedLabel: "WALL HDMI",
      unselectedLabel: "WALL HDMI",
      selectedColor: "blue",
      unselectedColor: "gray",
    },
    {
      selectedLabel: "FLOOR HDMI",
      unselectedLabel: "FLOOR HDMI",
      selectedColor: "blue",
      unselectedColor: "gray",
    },
    {
      selectedLabel: "AIR MEDIA",
      unselectedLabel: "AIR MEDIA",
      selectedColor: "blue",
      unselectedColor: "gray",
    },
  ];

</script>

<div>
<div id="scaling-container">
  <div id="page-container">
    <!-- Main Screen Section -->
    <VideoControls title="MAIN SCREEN" inputSources={inputSources} screenCount={3} />
    <VideoControls title="SIDE SCREEN" inputSources={inputSources} screenCount={3} />
    <Footer />
  </div>
</div>
</div>

<style>

</style>

