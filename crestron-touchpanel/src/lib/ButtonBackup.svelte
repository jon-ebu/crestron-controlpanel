<script>
    export let selectedLabel = "Selected";
    export let unselectedLabel = "Unselected";
    export let selectedColor = "green";
    export let unselectedColor = "red";
    export let isSelected = false; // Controlled externally or toggled internally
    export let isHtml = false; // New prop to determine if labels should be rendered as HTML
    export let onClick = null; // Optional callback for parent control
  
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
      font-size: 32px;
      font-weight: bold;
      border: none;
      cursor: pointer;
      border-radius: 20px;
      width: 200px;
      height: 120px;
      text-align: center;
      white-space: wrap;
      transition: all 0.3s ease; /* Smooth transition for animations */
    }
  
    button.on {
      box-shadow: 0 0 15px rgba(0, 255, 0, 0.7); /* Glow effect for "on" state */
      transform: scale(1.05); /* Slightly enlarge the button for tactile feedback */
    }
  
    button.off {
      box-shadow: 0 0 15px rgba(255, 0, 0, 0.7); /* Glow effect for "off" state */
      transform: scale(1); /* Normal size for "off" state */
    }
  
    button:active {
      transform: scale(0.95); /* Slight shrink effect when clicked */
    }
  </style>
  