<script>
  import Button from '$lib/Button.svelte';
  import ButtonGroup from '$lib/ButtonGroup.svelte';
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
      selectedLabel: "Option 1",
      unselectedLabel: "Option 1",
      selectedColor: "blue",
      unselectedColor: "gray"
    },
    {
      selectedLabel: "Option 2",
      unselectedLabel: "Option 2",
      selectedColor: "blue",
      unselectedColor: "gray"
    },
    {
      selectedLabel: "Option 3",
      unselectedLabel: "Option 3",
      selectedColor: "blue",
      unselectedColor: "gray"
    }
  ]}
/>