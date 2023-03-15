<script lang="ts">
  import Lookup from './lib/Lookup.svelte'
  import { data } from './lib/store';
  import WeatherData from './lib/WeatherData.svelte';

  let weather;

  data.subscribe(val => {
    weather = val
  })
</script>

<main>
  {#if weather}
    <WeatherData result={$data} />
    {:else}
      <Lookup />
  {/if}
</main>