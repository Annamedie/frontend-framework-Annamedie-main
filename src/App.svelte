<script lang="ts">
  const years = [2016,2017,2018,2019,2020,2021,2022];
</script>
<header>
<h1>
  The state of Javascript
</h1>
</header>
<main>
  <ul class="years">
    {#each years as year}
      <li>{year}</li>
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
