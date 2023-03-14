<script lang="ts">
  import Lookup from './lib/Lookup.svelte'
  import { data } from './lib/store';

  let weatherData;

  data.subscribe(val => {
    weatherData = val
  })
</script>

<main>
  <Lookup />
  {JSON.stringify($data)}
</main>