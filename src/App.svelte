<script>
  import Reserve from "./components/Reserve.svelte";
  function randomInt(min, max) {
    return Math.floor(Math.random() * (max - min + 1) + min);
  }

  let reserveArray = new Array(randomInt(3, 8)).fill(0);
</script>

<main>
  <h1>Wildtierreservate</h1>
  <div class="reserves">
    {#each reserveArray as _, i}
      <Reserve
        width={randomInt(100, 300)}
        height={randomInt(100, 300)}
        plants={randomInt(0, 100)}
        gnus={randomInt(3, 20)}
        hyenas={randomInt(1, 10)}
        id={i}
      />
    {/each}
  </div>
</main>

<style>
  .reserves {
    max-width: 800px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: wrap;
    gap: 20px;
  }

</style>
