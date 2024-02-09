<script lang="ts">
  import { frameworks } from '../data/index.js';

  const url = "awareness";
</script>
<header>
<h1>
  The state of Javascript
</h1>
</header>
<main>
  <ul data-cy="chart" class="chart">
    <li data-cy="chart-header-cell"></li>
    {#each frameworks[0].surveys as survey}
      <li data-cy="chart-header-cell">{survey.year}</li>
    {/each}
    <li data-cy="chart-header-cell"></li>

    {#each frameworks as {name, color, surveys }}
      <h2 data-cy="chart-data-cell" style="color: {color};">{name}</h2>

        <!-- Skapa tomma celler för de undersöknar som saknas: surveys[0].year - 2016 = 3 -->
      
        {#each surveys as survey }
          <li data-cy="chart-data-cell">
            <div data-cy="chart-circle">{survey[url]}%</div>
          </li>    
        {/each}
      
      <h2 data-cy="chart-data-cell" style="color: {color};">{name}</h2>
    {/each}
  </ul>
</main>
<style>
  .chart {
    display: grid;
    grid-template-columns: repeat(9, 1fr);
  }
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
