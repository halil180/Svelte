<script>
  import {fade,fly} from "svelte/transition"
  let count = 0
  const increment = () => {
    count += 1
  }

  let random;
  function setRandom() {
    random = Math.random().toFixed();
    randoms = [...randoms,random]
  }


  let randoms = []

</script>

<button on:click={increment}>
  count is {count}
</button>

 <!-- {random}
{Math.round(random)}

<p> {Math.round(random) ? "winner" : "loser"}</p> -->


<!-- <button on:click={setRandom}>
randomize
</button> -->


{#if count > 4}
  <h1 transition:fade> you clicked more than 4  that's awesome!!!! </h1>
{:else}

<h1 
  out:fly={{x:-500,duration:500}}
>loser until you click more than 4 times :(</h1>

{/if}


<button on:click={setRandom}>push a random number (0 or 1)</button>

<ul>
    {#each randoms as random, idx}
    <li>{random}</li>
    {/each}

</ul>