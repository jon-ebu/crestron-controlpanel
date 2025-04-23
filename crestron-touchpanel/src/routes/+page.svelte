<script>
  import Button from "$lib/Button.svelte";
  import ButtonGroup from "$lib/ButtonGroup.svelte";
  import VolumeSlider from "$lib/VolumeSlider.svelte";

  let volume = 50;

  function handleVolumeChange(newVolume) {
    volume = newVolume;
    console.log("Volume changed to:", volume);
  }
</script>

<div id="main-screen">
  <h1>MAIN SCREEN</h1>
  <div class="controls-container">
    <div class="buttons-container">
      <Button
        selectedLabel="On"
        unselectedLabel="Off"
        selectedColor="blue"
        unselectedColor="gray"
      />
      <Button
        selectedLabel="Video Mute On"
        unselectedLabel="Video Mute Off"
        selectedColor="blue"
        unselectedColor="gray"
      />
      <ButtonGroup
        buttons={[
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
        ]}
      />
    </div>
  </div>
  <div id="side-screen">
    <h1>SIDE SCREEN</h1>
    <div class="controls-container">
      <div class="buttons-container">
        <Button
          selectedLabel="On"
          unselectedLabel="Off"
          selectedColor="blue"
          unselectedColor="gray"
        />
        <Button
          selectedLabel="Video Mute On"
          unselectedLabel="Video Mute Off"
          selectedColor="blue"
          unselectedColor="gray"
        />
        <ButtonGroup
          buttons={[
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
          ]}
        />
      </div>
    </div>
  </div>

  <VolumeSlider value={volume} onChange={handleVolumeChange} />
</div>

<style>
  .controls-container {
    display: flex;
    flex-direction: column;
    gap: 20px;
    align-items: center;
    padding: 20px;
  }

  .buttons-container {
    display: flex;
    gap: 10px;
    flex-wrap: wrap; /* Allow buttons to wrap if needed */
    justify-content: center;
  }
</style>
