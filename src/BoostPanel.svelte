<script>
    import PlayerBoost from "./PlayerBoost.svelte";
    export let team;
    export let num=0;
  </script>
  <style>
  </style>
  <div class='main'>
    {#each team as p}
      {#if p.team==num}
        {#if num==0}
          <PlayerBoost name={p.name} boost={p.boost} color={'blue'} isDead={p.isDead}></PlayerBoost>
        {:else}
          <PlayerBoost name={p.name} boost={p.boost} color={'orange'} isDead={p.isDead}></PlayerBoost>
        {/if}
      {/if} 
   {/each}
  </div>
  