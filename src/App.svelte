<script lang="ts">
  import { frameworks } from '../data/index.js';

  const url = "retention";
</script>
<header>
<h1>
  The state of Javascript
</h1>
</header>
<main>
  <div data-cy="chart" class="chart">
    <div data-cy="chart-header-cell"></div>
    {#each frameworks[0].surveys as survey}
      <div data-cy="chart-header-cell">{survey.year}</div>
    {/each}
    <div data-cy="chart-header-cell"></div>

    {#each frameworks as {name, color, surveys }}
      <h2 data-cy="chart-data-cell" style="color: {color};">{name}</h2>

        <!-- Skapa tomma celler för de undersöknar som saknas: surveys[0].year - 2016 = 3 -->
        {#each {length: surveys[0].year - 2016} as _,i }
          <div>{i+1}</div>
        {/each}
      
        {#each surveys as survey }
          <li data-cy="chart-data-cell">
            <div data-cy="chart-circle">{survey[url]}%</div>
          </li>    
        {/each}
      
      <h2 data-cy="chart-data-cell" style="color: {color};">{name}</h2>
    {/each}
        </div>
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
  div{
    color: azure;
    width: 30px;
    height: 30px;
    border:1px solid blue;
    border-radius: 50%;
  }
</style>
