<script>
  import Button from "./Button.svelte";
  import ButtonGroup from "./ButtonGroup.svelte";
  export let title = "Default Title"; // Configurable title
  export let inputSources = []; // Configurable array of input sources
</script>

<div class="box">
  <div class="header-container">
    <h1>{title}</h1>
    <div class="controls-container">
      <div class="buttons-container">
        <div class="group">
          <div>
            <div class="input-label">Projector Controls</div>
            <Button
              selectedLabel="POWER OFF"
              unselectedLabel="POWER ON"
              selectedColor="red"
              unselectedColor="green"
              isHtml={true}
            />
            <Button
              selectedLabel="VIDEO MUTE"
              unselectedLabel="VIDEO MUTE"
              selectedColor="BLACK"
              unselectedColor="lightgray"
            />
          </div>
        </div>
        <div class="group">
          <div class="input-label">Input Sources (select one)</div>
          <ButtonGroup buttons={inputSources} />
        </div>
      </div>
    </div>
  </div>
</div>
<style>
  .box {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 20px;
    margin: 10px;
    background-color: #f9f9f9;
    border: 2px solid #878787;
    border-radius: 10px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
  }

  .header-container {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 20px;
  }

  h1 {
    font-size: 1.5rem;
    margin: 0;
  }

  .controls-container {
    display: flex;
    flex-direction: column;
    gap: 40px;
    width: 100%;
    height: 100%;
  }

  .buttons-container {
    display: flex;
    flex-direction: row;
    gap: 40px;
    justify-content: center;
    align-items: flex-end;
    flex: 1;
    flex-wrap: nowrap;
  }

  .group {
    display: flex;
    flex-direction: column;
    gap: 10px;
    align-items: center;
    justify-content: flex-end;
    flex: 1;
  }

  .input-label {
    text-align: center;
    font-weight: bold;
    font-size: 1.2rem;
    margin-bottom: 10px;
    width: 100%;
  }

  button {
    font-size: 1rem;
    padding: 15px 20px;
  }
</style>
