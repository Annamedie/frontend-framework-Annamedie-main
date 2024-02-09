<script lang="ts">
  import { frameworks } from '../data/index.js';
</script>
<header>
<h1>
  The state of Javascript
</h1>
</header>
<main>
  <ul class="years">
    {#each frameworks as {name}}
      <li>{name}</li>
    {/each}
  </ul>
</main>
<style>
  h1{
    display: flex;
    justify-content: center;
    color: white;
    font-size: 5em;
  }
  li{
    color: white;
  }
</style>
