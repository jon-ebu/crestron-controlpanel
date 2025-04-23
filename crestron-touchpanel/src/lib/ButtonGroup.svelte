<script>
  import Button from './Button.svelte';

  export let buttons = []; // Array of button configurations
  export let selectedIndex = 0; // Index of the initially selected button

  function selectButton(index) {
    selectedIndex = index;
  }
</script>

<div class="button-group">
  {#each buttons as button, index}
    <Button
      selectedLabel={button.selectedLabel}
      unselectedLabel={button.unselectedLabel}
      selectedColor={button.selectedColor}
      unselectedColor={button.unselectedColor}
      on:click={() => selectButton(index)}
      isSelected={index === selectedIndex}
    />
  {/each}
</div>

<style>
  .button-group {
    display: flex;
    gap: 10px; /* Space between buttons */
  }
</style>