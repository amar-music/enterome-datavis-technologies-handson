<script>
  let current = "";

  function isCurrent(player) {
    return current === player;
  }
</script>

<style>
  .current {
    background-color: red;
  }
</style>


<!-- We will cover buttons later on! -->
<button class="btn btn-secondary" on:click={() => (current = "messi")}>
  Messi
</button>

<button class="btn btn-secondary" on:click={() => (current = "ronaldo")}>
  Ronaldo
</button>

<button class="btn btn-secondary" on:click={() => (current = "neymar")}>
  Neymar
</button>
