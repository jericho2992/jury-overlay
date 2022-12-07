<svelte:options accessors></svelte:options>
<script>
  import PlayerBoost from "./PlayerBoost.svelte";
  import BoostPanel from "./BoostPanel.svelte";
  import Scoreboard from "./Scoreboard.svelte";
  export let players=[];
  export let tNames=['BLUE', 'ORANGE'];
  export let time=300;
  export let OT=false;
  export let tScores = [0,0];
  export let focus="";
</script>

<style>
  .main {
    min-width: 100vw;
    text-align: center;
    display: flex;
    flex-direction: row;
    justify-content: center;
    margin-top: 0;
  }
  .boost-wrap {
    width: 300px;
    position: absolute;
    top: 0px;
  }
  .sam-cam {
    position: fixed;
    min-width: 150px;
    padding: 10px;
    bottom: 0;
    left: 50%;
    right: 50%;
    background: black;
    text-align: center;
    color: red;
  }
  #right-boost {
    right: 0px;
  }
  #left-boost {
    left: 0px;
  }
  
</style>
<div class='main'>
    <div class='boost-wrap' id='left-boost'>
    <BoostPanel team={players} num={0} ></BoostPanel>
  </div>
  <div class='boost-wrap' id='right-boost'>
    <BoostPanel team={players} num={1}> </BoostPanel>
  </div>
  <div class='sb-wrap'>
    <Scoreboard lTeamName={tNames[0]} rTeamName={tNames[1]} lTeamScore={tScores[0]} rTeamScore={tScores[1]} time={time} OT={OT}></Scoreboard>
  </div>
</div>
  
  {#if focus.includes("rinz")}
    <div class="sam-cam">
      <h2>Sam is stinky</h2>
      <img src="/images/poop.png" alt="sam bad">
    </div>div>
  {/if}

