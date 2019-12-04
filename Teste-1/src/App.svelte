<script>
  import Template from "./template.svelte";

  let items = [];
  let value = 0;

  function handleAddItem() {
    value += 1;
    items[items] = items.push({ name: `teste ${value}` });
    console.log(items);
  }
</script>

<style>
  main {
    text-align: left;
    padding: 1em;
    max-width: 240px;
    margin: 0 1em;
  }
</style>

<main>
  <button on:click={handleAddItem}>Adicionar item</button>

  {#each items as item}
    <Template name={item.name} />
  {/each}

</main>
