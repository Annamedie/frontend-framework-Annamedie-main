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
    {#each frameworks as {name, color, surveys }}
      <h2 style="color: {color};">{name}</h2>
      <ul>
        {#each surveys as {year, retention } }
        <li >
          {year}
        </li>
        <li>{retention}%</li>
          
        {/each}
      </ul>
      <h2 style="color: {color};">{name}</h2>
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
  h2{
    color: white;
  }
  li{
    list-style: none;
    color: white;
  }
</style>
