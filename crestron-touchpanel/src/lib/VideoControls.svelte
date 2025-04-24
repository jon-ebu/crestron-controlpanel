<script>
    import Button from './Button.svelte';
    import ButtonGroup from './ButtonGroup.svelte';
  
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
                selectedLabel="<i class='bi bi-power' style='font-size: 4rem; line-height: 0;'></i>"
                unselectedLabel="<i class='bi bi-power' style='font-size: 4rem; line-height: 0;'></i>"
                selectedColor="red"
                unselectedColor="green"
                isHtml={true}
              />
              <Button
                selectedLabel="VIDEO MUTE"
                unselectedLabel="VIDEO MUTE"
                selectedColor="blue"
                unselectedColor="gray"
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
      justify-content: center; /* Center content vertically */
      align-items: center; /* Center content horizontally */
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
      align-items: center; /* Center header horizontally */
      text-align: center;
      gap: 20px;
    }
  
    h1 {
      font-size: 3rem;
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
      flex-direction: row; /* Arrange groups in a single row */
      gap: 40px; /* Add space between groups */
      justify-content: center; /* Center groups horizontally */
      align-items: flex-end; /* Align groups at the bottom */
      flex: 1;
      flex-wrap: nowrap; /* Prevent wrapping to a new row */
    }
  
    .group {
      display: flex;
      flex-direction: column; /* Stack elements vertically within each group */
      gap: 10px;
      align-items: center; /* Center elements horizontally */
      justify-content: flex-end; /* Align elements at the bottom */
      flex: 1; /* Ensure groups take equal space */
    }
  
    .input-label {
      text-align: center;
      font-weight: bold;
      font-size: 1.2rem;
      margin-bottom: 10px; /* Add consistent spacing below the label */
      width: 100%;
    }
  </style>