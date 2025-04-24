<script>
    export let title = "MAIN SCREEN";
    export let projectorControls = [];
    export let inputSources = [];
</script>
  <div class="box">
    <div id="main-screen">
      <div class="header-container">
        <h1>{title}</h1>
        <div class="controls-container">
          <div class="buttons-container">
            <div class="group">
              <div class="input-label">Projector Controls</div>
              {#each projectorControls as control}
                <Button
                  selectedLabel={control.selectedLabel}
                  unselectedLabel={control.unselectedLabel}
                  selectedColor={control.selectedColor}
                  unselectedColor={control.unselectedColor}
                />
              {/each}
            </div>
            <div class="group">
              <div class="input-label">Input Sources</div>
              <ButtonGroup buttons={inputSources} />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  
  <style>
    .box {
  display: flex;
  flex-direction: column;
  gap: 20px;
}

.controls-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.buttons-container {
  display: flex;
  flex-direction: column;
  gap: 10px;
}

.group {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 10px;
}

.input-label {
  text-align: center;
  font-weight: bold;
  font-size: 1.2rem;
  margin-bottom: 10px;
}
  </style>