<script lang="ts">
    import { data } from "./store";
    let lookup: string;

    function searchData() {
        data.set({
            'location': lookup
        })
    }
</script>

<div>
    <div class="container">
        <h1 class="title">How's<br>the<br>weather?</h1>
        <form class="form-body" on:submit|preventDefault={searchData}>
            <input type="text" placeholder="Enter LOCATION then press RETURN" bind:value={lookup}>
            <button type="submit">RETURN</button>
        </form>
    </div>
</div>

<style>
    .container {
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }
    h1.title {
        font-family: 'Bebas Neue', Impact, Haettenschweiler, 'Arial Narrow Bold', sans-serif;
        font-size: 3rem;
    }
    form.form-body {
        display: flex;
        align-items: center;
        justify-content: center;
    }
    input[type=text] {
        background: transparent;
        color: #fff;
        padding: 1em 0.75em;
        border: none;
        min-width: 30vw;
        border: rgb(232,81,18) solid 3px;
        border-right: none;
    }
    button {
        background-color: rgb(232,81,18);
        border: none;
        height: 2.9rem;
        padding: 1.3em 3em;
        cursor: pointer;
    }
</style>