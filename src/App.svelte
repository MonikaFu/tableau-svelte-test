<script>

  import { TableauViz, TableauEventType } from '@tableau/embedding-api';

</script>

<main>
  <h1>Embedding Tableau in a Svelte app - test</h1>
  <p>
    Using the <a href="https://learn.svelte.dev/">Embedding API</a> to embed public Tableau vizzes 
    in an app and interact with them.
  </p>
  <div style="width:800px; height:700px;">

    <!-- Initialization of the Tableau visualization via web component. See more properties here:
    https://help.tableau.com/current/api/embedding_api/en-us/docs/embedding_api_configure.html -->
    <tableau-viz id="tableauViz" src="https://public.tableau.com/views/RegionalSampleWorkbook/Storms"
        toolbar="bottom" hide-tabs>
    </tableau-viz>
  </div>
  <div style="width:800px; height:700px;">
    <tableau-viz id="tableauViz2" src="https://public.tableau.com/views/RegionalSampleWorkbook/College"
        toolbar="bottom" hide-tabs>
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
