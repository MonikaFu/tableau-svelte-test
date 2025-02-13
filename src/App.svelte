<script>

  import { TableauViz, TableauEventType } from '@tableau/embedding-api';
  import { onMount } from 'svelte';
    import { on } from 'svelte/events';

  onMount(async () => {
    const viz = document.querySelector("#tableauViz");

    viz.src = "https://public.tableau.com/views/RegionalSampleWorkbook/College";
    viz.addEventListener(TableauEventType.ParameterChanged, handleFilterChange);

    /*  Methods */
    
    function handleFilterChange() {
      alert('Mark(s) selected!');
      // code to handle the mark selection goes here
    }

    function handleFirstInteractive(e) {
            console.log("---handleFirstInteractive---");
            console.log("Viz Embedding Successful!");
        }
  }
)
  

</script>

<main>
  <h1 id="title">Embedding Tableau in a Svelte app - test</h1>
  <p>
    Using the <a href="https://help.tableau.com/current/api/embedding_api/en-us/index.html">Tableau Embedding API</a> to embed public Tableau vizzes 
    in an app and interact with them.
  </p>
  <div style="width:900px; height:700px;">
    <tableau-viz id="tableauViz"></tableau-viz>
  </div>
  <div style="width:900px; height:700px;">
    <tableau-viz id="tableauViz2" src="https://public.tableau.com/views/RegionalSampleWorkbook/College"
       toolbar="bottom" hide-tabs>
        <viz-filter field="College" value="Business"></viz-filter>

    </tableau-viz>
  </div>
</main>

<style>
  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  h1 {
    color: #770304;
    font-size: 3em;
    font-weight: 100;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
