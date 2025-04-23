<script>
  export let value = 50; // Initial volume value (0-100)
  export let onChange = null; // Optional callback for parent control

  function handleInput(event) {
    value = +event.target.value;
    if (onChange) {
      onChange(value);
    }
  }
</script>

<style>
  .slider-container {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .icon {
    width: 24px;
    height: 24px;
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .slider {
    -webkit-appearance: none;
    appearance: none;
    width: 100%;
    height: 10px;
    background: #f0f0f0;
    border-radius: 5px;
    outline: none;
    overflow: hidden;
    position: relative;
  }

  .slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 20px;
    height: 20px;
    background: #007bff;
    border-radius: 50%;
    cursor: pointer;
    position: relative;
    z-index: 2;
  }

  .slider::-moz-range-thumb {
    width: 20px;
    height: 20px;
    background: #007bff;
    border-radius: 50%;
    cursor: pointer;
  }

  .slider::-ms-thumb {
    width: 20px;
    height: 20px;
    background: #007bff;
    border-radius: 50%;
    cursor: pointer;
  }

  .slider::-webkit-slider-runnable-track {
    background: linear-gradient(to right, #f0ad4e 0%, #f0ad4e var(--value, 50%), #f0f0f0 var(--value, 50%), #f0f0f0 100%);
  }

  .slider::-moz-range-progress {
    background: #f0ad4e;
  }

  .slider::-ms-fill-lower {
    background: #f0ad4e;
  }
</style>

<div class="slider-container">
  <div class="icon">🔈</div>
  <input
    type="range"
    min="0"
    max="100"
    value={value}
    class="slider"
    style="--value: {value}%"
    on:input={handleInput}
  />
  <div class="icon">🔊</div>
</div>