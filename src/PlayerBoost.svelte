<script>
    export let name='Player';
    export let boost=0;
    export let color='blue';
    export let isDead=false;
  </script>
  <style>
      h4 {
          margin: 10px;
          padding: 0;
      }
      .main {
          display: flex;
          flex-direction: column;
          flex-wrap: nowrap;
          justify-items: flex-start;
          justify-content: flex-start;
          color: white;
      }
      .text {
          display: flex;
          flex-direction: row;
          flex-wrap: nowrap;
          justify-content: space-between;
          margin-bottom: 5px;
      }
      .boost-bar {
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: center;
        margin-bottom: 5px;
      }
      .empty-bar {
        background-color: rgb(37, 37, 37);
        min-width: 250px;
        max-width: 250px;
        min-height: 3px;
        display: flex;
        flex-direction: row;
        flex-wrap: nowrap;
        justify-content: flex-start;
        border-radius: 3px;
      }
  </style>
  {#if !isDead}
  <div class='main' style="background-image: linear-gradient(black,{color}">
    <div class='text'>
      <div class='name-div'>
          <h4>{name}</h4>
      </div>
      <div class='boost-num'>
          <h4>{boost}</h4>
      </div>
    </div>
    <div class='boost-bar'>
      <div class='empty-bar'>
        <div class='fullbar' style="background-color: white; border-radius: 3px; white; min-width: {boost/100*240}px; max-width: {boost/100*240}px"></div>
      </div>
    </div>
  </div>
  {:else}
  <div class='main' style="background-color: red">
      <div class='text'>
        <div class='name-div'>
            <h4>{name}</h4>
        </div>
        <div class='boost-num'>
            <h4>dead</h4>
        </div>
      </div>
      <div class='boost-bar'>
        <div class='empty-bar'>
          <div class='fullbar' style="background-color: white; border-radius: 3px; white; min-width: {boost/100*190}px; max-width: {boost/100*190}px"></div>
        </div>
      </div>
    </div>
  {/if}