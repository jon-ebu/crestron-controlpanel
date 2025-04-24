<script>
  import VideoControls from "$lib/VideoControls.svelte";
  import Footer from "$lib/Footer.svelte"; // Verify this path and ensure Footer.svelte is correctly exported
  import "../app.css"; // Ensure this path is correct


  // Check the total height on mount
  import { onMount } from "svelte";
  onMount(() => {
    const totalHeight = getTotalDivHeight();
    if (totalHeight > 5815) {
      isPageTooTall = true;
    }
  });


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
    <VideoControls title="MAIN SCREEN" inputSources={inputSources} />
    <VideoControls title="SIDE SCREEN" inputSources={inputSources} />
    <Footer />
  </div>
</div>
</div>

<style>

</style>

