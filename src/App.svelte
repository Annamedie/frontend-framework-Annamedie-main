<script lang="ts">
  import { frameworks } from '../data/index.js';

  const url = "retention";
</script>
<header>
<h1>
  State of Javascript
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
          <div class="tom-cell" data-cy="chart-data-cell"></div>
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
<footer></footer>
<style>
 
 main{
  margin: 5em;
 }
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
    font-size: 3em;
    display: flex;
    justify-content: center;
    color: white;
    
  }
  .header-cell{
    color: white;
    font-size: larger;
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
  footer{
    height: 5em;
    background-color: black;
  }
  .tom-cell{
    height: 10px;
    width: 10px;
  }


 
</style>
