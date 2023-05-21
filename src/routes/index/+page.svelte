<script lang="ts">
  import { apiResults } from '../..//lib/store'
  import Form from '../../lib/Form.svelte'
  let data;
  let value: string;

  apiResults.subscribe(val => {
    data = val
  });

  function submit() {
    alert(value)
  }
</script>

<svelte:head>
  <title>weather-png</title>
</svelte:head>

<main>
  <div class="main-content">
    <h1>weather.png</h1>
    <p>A simple app that shows the weather from <a href="://openweathermap.org" target="_blank" referrerpolicy="no-referrer">OpenWeatherMap</a> and generates an birds eye view of the city from <a href="://https://openai.com/product/dall-e-2" target="_blank" referrerpolicy="no-referrer">DALL-E </a> with the corresponding weather.</p>
    <Form bind:value onSubmitForm={submit}/>
    <footer>
      &copy; 2023 - A <a href="://torten.xyz">tortenworx</a> project
    </footer>
  </div>
  <img class="image-result" src="/Rectangle.png" alt="" srcset="Image result">
</main>

<style lang="scss">
  @import '../../styles/mixins';

  main {
    min-height: 100vh;
    display: flex;
    flex-direction: column-reverse;
    align-items: center;
    justify-content: start;
    @include md {
      flex-direction: row;
      max-height: 100vh;
    }
  }

  .main-content {
    background: url('/Rectangle.png');
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    @include md {
      background: #222 !important;
    }
    color: #fff;
    height: 100vh;
    display: flex;
    align-items: center;
    flex-direction: column;
    justify-content: center;
    padding: 1em 3em;
    h1 {
      font-family: 'Righteous', cursive;
      font-size: 2.8rem;
      text-align: center;
    }
    p {
      font-family: 'Inter', sans-serif;
    }
    a {
      color: #fff;
    }
    footer {
      margin-top: 0.73em;
      font-family: 'Rubik', sans-serif;
      color: rgba(255, 255, 255, 0.25);
      a {
        color: rgba(255, 255, 255, 0.25);
      }
    }
  }

  img.image-result {
    width: 100%;
    visibility: none;
    display: none;
    @include md {
      width: auto;
      visibility: visible;
      display: block;
      min-height: 100vh;
    }
  }
</style>
