<script>
  export let selectedLabel = "Selected";
  export let unselectedLabel = "Unselected";
  export let selectedColor = "green";
  export let unselectedColor = "red";
  export let isSelected = false; // Controlled externally or toggled internally
  export let onClick = null; // Optional callback for parent control

  function handleClick() {
    if (onClick) {
      // If a parent callback is provided, use it
      onClick();
    } else {
      // Otherwise, toggle the state internally
      isSelected = !isSelected;
    }
  }
</script>

<style>
  button {
    padding: 10px 20px;
    font-size: 16px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
    width: 150px;
    text-align: center;
    white-space: nowrap;
  }
</style>

<button
  on:click={handleClick}
  style="background-color: {isSelected ? selectedColor : unselectedColor}; color: white;"
>
  {isSelected ? selectedLabel : unselectedLabel}
</button>