<script>
  import VolumeSlider from "./VolumeSlider.svelte";
  import Button from "./Button.svelte";

  let volume = 50; // Initialize the volume variable

  function handleVolumeChange(event) {
    volume = event.detail; // Update the volume based on the event's detail
    console.log("Volume changed to:", volume); // Log for debugging
  }
</script>

<div id="footer">
  <div class="slider-wrapper">
    <!-- Ensure the VolumeSlider emits a 'change' event with the new volume -->
    <VolumeSlider value={volume} on:change={handleVolumeChange} />
  </div>
  <Button
    class="turn-off-system"
    selectedLabel="Turn Off System"
    unselectedLabel="Turn Off System"
    selectedColor="red"
    unselectedColor="red"
  />
</div>

<style>
  :global(#footer .turn-off-system) {
    background-color: rgb(255, 0, 0)(8, 5, 5);
    color: white;
    border: 2px solid red;
    padding: 10px 20px;
    border-radius: 5px;
    cursor: pointer;
    width: 200px;
    height: 100px;
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
</style>
