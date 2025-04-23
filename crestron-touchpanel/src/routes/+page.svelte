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
    <div class="header-container">
      <h1>MAIN SCREEN</h1>
      <div class="controls-container">
        <div class="buttons-container">
          <div class="group">
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
          </div>
          <div class="group">
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
    </div>
  
    <VolumeSlider value={volume} onChange={handleVolumeChange} />
  </div>
  
  <style>
        * {
        font-family: Helvetica, Arial, sans-serif; /* Use Helvetica as the primary font */
    }

    .header-container {
      display: flex;
      flex-direction: column;
      gap: 20px;
      align-items: left;
      padding: 20px;
      border: 2px solid #ccc; /* Same border as VolumeSlider */
      border-radius: 10px; /* Rounded corners */
      background-color: #fff; /* White background */
      box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1); /* Subtle shadow */
    }
  
    .controls-container {
      display: flex;
      flex-direction: column;
      gap: 20px;
      align-items: left;
    }
  
    .buttons-container {
      display: flex;
      gap: 40px; /* Space between groups */
      justify-content: left;
    }
  
    .group {
      display: flex;
      gap: 10px; /* Space between buttons within a group */
    }
  </style>