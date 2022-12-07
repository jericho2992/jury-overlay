<script>
    export let lTeamName;
    export let rTeamName;
    export let lTeamScore;
    export let rTeamScore;
    export let time;
    export let OT;
    $: seconds= time%60;
    $: minutes= Math.floor(time/60); 
  </script>
  <style>
  h1 {
      margin: 0;
      padding: 0;
  }
  .main {
      margin-top: 0;
      color: white;
      display: flex;
      flex-direction: row;
      flex-wrap: nowrap;
      background-color: black;
      align-items: center;
      clip-path: polygon(0% 0%, 100% 0%, 95% 100%, 5% 100%);
  }
  .l-team {
      display: flex;
      flex-direction: row;
      flex-wrap: nowrap;
      margin-right: 20px;
  }
  .r-team {
      display: flex;
      flex-direction: row;
      flex-wrap: nowrap;
      margin-left: 20px;
  }
  .l-team-name {
      padding: 20px 30px;
      min-width: 250px;
      text-align: right;
      text-shadow: 0.2em 0.2em black;
      background-image: linear-gradient(black, blue);
  }
  .r-team-name {
      padding: 20px 30px;
      min-width: 250px;
      text-align: left;
      text-shadow: 0.2em 0.2em black;
      background-image: linear-gradient(black, orange);
  }
  .l-team-score {
      background-color: blue;
      padding: 20px 30px;
      text-shadow: 0.2em 0.2em black;
  }
  .r-team-score {
      background-color: orange;
      padding: 20px 30px;
      text-shadow: 0.2em 0.2em black;
  }
  .clock{
      padding: 10px;
      min-width: 100px;
  }
  </style>
  <div class='main'>
    <div class='l-team'>
       <div class='l-team-name'>
           <h1>{lTeamName}</h1>
       </div>
       <div class='l-team-score'>
           <h1>{lTeamScore}</h1>
      </div>
    </div>
    <div class='clock'>
        {#if !OT}
            {#if seconds<10}
               <h1>{minutes}:0{seconds}</h1>
            {:else}
               <h1>{minutes}:{seconds}</h1>
            {/if}
        {:else}
            {#if seconds<10}
              <h1>+{minutes}:0{seconds}</h1>
           {:else}
              <h1>+{minutes}:{seconds}</h1>
           {/if}
        {/if}
    </div>
    <div class='r-team'>
       <div class='r-team-score'>
           <h1>{rTeamScore}</h1>
       </div>
       <div class='r-team-name'>
           <h1>{rTeamName}</h1>
      </div>
    </div>
  </div>