<script>
  import Button from "$lib/Button.svelte";
  import ButtonGroup from "$lib/ButtonGroup.svelte";
  import ControlGroup from "$lib/ControlGroup.svelte";
  import VideoControls from "$lib/VideoControls.svelte";
  import VolumeSlider from "$lib/VolumeSlider.svelte";

  let volume = 50;

  function handleVolumeChange(newVolume) {
    volume = newVolume;
    console.log("Volume changed to:", volume);
  }

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

<div id="scaling-container">
  <div id="page-container">
    <!-- Main Screen Section -->
    <VideoControls title="MAIN SCREEN" inputSources={inputSources} screenCount={1} />
    <VideoControls title="SIDE SCREEN" inputSources={inputSources} screenCount={1} />

    <!-- Footer -->
    <div id="footer">
      <div class="slider-wrapper">
        <VolumeSlider value={volume} onChange={handleVolumeChange} />
      </div>
      <Button
        selectedLabel="Turn Off System"
        unselectedLabel="Turn Off System"
        selectedColor="red"
        unselectedColor="red"
      />
    </div>
  </div>
</div>

<style>
  * {
    font-family: Helvetica, Arial, sans-serif;
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  html,
  body {
    margin: 0;
    padding: 0;
    width: 100vw;
    height: 100vh;
    overflow: hidden;
  }

  #scaling-container {
    width: 100vw;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: #f0f0f0;

    /* Scale content based on window vs. target 1280x800 size */
    zoom: calc(min(100vw / 1280, 100vh / 800));
    transform-origin: top left;
  }

  #page-container {
    width: 1280px;
    height: 800px;
    display: flex;
    flex-direction: column;
    background-color: #fff;
    border: 2px solid #ccc;
    border-radius: 10px;
    box-shadow: 0 4px 10px rgba(0, 0, 0, 0.1);
    overflow: hidden;
  }

  #footer {
    display: flex;
    align-items: center;
    gap: 20px;
    padding: 10px 20px;
    background-color: #f9f9f9;
    border-top: 2px solid #ccc;
    flex-shrink: 0;
  }

  .slider-wrapper {
    flex: 6;
  }

  #footer > Button {
    flex: 2;
  }
</style>