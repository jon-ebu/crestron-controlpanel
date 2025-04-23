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

<h1>MAIN SCREEN</h1>
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

<VolumeSlider value={volume} onChange={handleVolumeChange} />