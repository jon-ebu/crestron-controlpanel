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
      selectedLabel: "FLOOR HDMI 1",
      unselectedLabel: "FLOOR HDMI 1",
      selectedColor: "#304f30",
      unselectedColor: "#8FBC8F",
    },
    {
      selectedLabel: "FLOOR HDMI 2",
      unselectedLabel: "FLOOR HDMI 2",
      selectedColor: "#6A5ACD",
      unselectedColor: "#c2bceb"
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
    <VideoControls title="STAGE LEFT (HOUSE RIGHT)" inputSources={inputSources} />
    <VideoControls title="CENTER" inputSources={inputSources} />
    <VideoControls title="STAGE RIGHT (HOUSE LEFT)" inputSources={inputSources} />

    <Footer />
  </div>
</div>
</div>

<style>

</style>

