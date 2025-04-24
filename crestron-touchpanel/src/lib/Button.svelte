<script>
  let {
    selectedLabel = "Selected",
    unselectedLabel = "Unselected",
    selectedColor = "green",
    unselectedColor = "red",
    class: propsClass = "",
    isSelected = false, // Controlled externally or toggled internally
    isHtml = false, // New prop to determine if labels should be rendered as HTML
    onClick = null // Optional callback for parent control
  } = $props();

  function handleClick() {
    if (onClick) {
      onClick();
    } else {
      isSelected = !isSelected;
    }
  }

</script>

<button
  on:click={handleClick}
  class={propsClass}
  style="background-color: {isSelected
    ? selectedColor
    : unselectedColor}; color: white;"
>
  {#if isHtml}
    {@html isSelected ? selectedLabel : unselectedLabel}
  {:else}
    {isSelected ? selectedLabel : unselectedLabel}
  {/if}
</button>

<style>
  button {
    padding: 10px 20px;
    font-size: 30px;
    font-weight: bold;
    border: none;
    cursor: pointer;
    border-radius: 20px;
    width: 200px;
    height: 100px;
    text-align: center;
    white-space: wrap;
    transition: all 0.3s ease; /* Smooth transition for animations */
  }

  button.on {
    box-shadow: 0 0 15px rgba(0, 255, 0, 0.7); /* Glow effect for "on" state */
    transform: scale(
      1.05
    ); /* Slightly enlarge the button for tactile feedback */
  }

  button.off {
    box-shadow: 0 0 15px rgba(255, 0, 0, 0.7); /* Glow effect for "off" state */
    transform: scale(1); /* Normal size for "off" state */
  }

  button:active {
    transform: scale(0.95); /* Slight shrink effect when clicked */
  }
</style>
