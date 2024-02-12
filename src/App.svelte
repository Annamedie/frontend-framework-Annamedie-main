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
    
    <div data-cy="chart-header-cell" class="header-cell"></div>
    {#each frameworks[0].surveys as survey}
      <div data-cy="chart-header-cell" class="header-cell">{survey.year}</div>
    {/each}
    <div data-cy="chart-header-cell" class="header-cell"></div>
  
    {#each frameworks as {name, color, surveys }}
      <h2 data-cy="chart-data-cell" class= "data-cell-name" style="color: {color};">{name}</h2>

        <!-- Skapa tomma celler för de undersöknar som saknas: surveys[0].year - 2016 = 3 -->
        {#each {length: surveys[0].year - 2016} as _,i }
          <div>{i+1}</div>
        {/each}
      
        {#each surveys as survey }
          <div data-cy="chart-data-cell" style= "border-color: {color};"class="chart-data">
            <div data-cy="chart-circle" style= "color: {color}" >{survey[url]}%</div>
          </div>    
        {/each}
      
      <h2 data-cy="chart-data-cell" class= "data-cell-name" style="color: {color};">{name}</h2>
    {/each}
        </div>
</main>
<style>
 
  .chart {
    display: grid;
    grid-template-columns: repeat(9, 1fr);
    gap: 10px;
    justify-items: center;
    align-items: center;
    margin: auto;
    overflow-x: scroll;
   
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
  .chart-data{
    display:flex;
    justify-content: center;
    align-items: center;
    height: 50px;
    width: 50px;
    border-radius: 50%;
    border-style: solid;
  }


 
</style>
