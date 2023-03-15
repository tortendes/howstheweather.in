<script lang="ts">
  import { data } from "./store";

    export let result: any;
</script>

<main>
    {#if result.status == 0}
        <div class="not-found">
            <div class="container">
                <img src="/x-octagon.svg" alt="Not Found">
                <div>
                    <h1>Not Found</h1>
                    <h3>{result.message}</h3>
                    <a href="/">Go Back</a>
                </div>
            </div>
        </div>
    {/if}
    
</main>

<style lang="scss">
    .not-found {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 1em;
        min-height: 100vh;
        div.container {
            max-width: 70vw;
            display: flex;
            align-items: center;
            justify-items: center;
            gap: 1em;
        }
        & img {
            width: 12rem;
            height: auto;
            filter: invert(1);
        }
        h1 {
            font-weight: 800;
            margin-bottom: 0;
        }
        h3 {
            margin-top: 0.3em;
            font-size: 1em;
        }
    }
</style>