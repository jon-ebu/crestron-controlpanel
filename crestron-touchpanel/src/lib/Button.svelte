<script>
  export let selectedLabel = "Selected";
  export let unselectedLabel = "Unselected";
  export let selectedColor = "green";
  export let unselectedColor = "red";
  export let isSelected = false; // New prop to control the selected state

  function toggleState() {
    // No internal state toggle for grouped buttons
    if (!isSelected) {
      const event = new CustomEvent('click');
      dispatchEvent(event);
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
  on:click={toggleState}
  style="background-color: {isSelected ? selectedColor : unselectedColor}; color: white;"
>
  {isSelected ? selectedLabel : unselectedLabel}
</button>