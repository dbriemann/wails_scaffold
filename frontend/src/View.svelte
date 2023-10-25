<script>
    import { Greet } from "../wailsjs/go/main/App.js"

    export let page

    let resultText = "Please enter your name below 👇"
    let name
    function greet() {
        Greet(name).then((result) => (resultText = result))
    }
</script>

{#if page == 0}
    <p>Hi from page 0</p>
    <div class="result" id="result">{resultText}</div>
    <div class="input-box" id="input">
        <input autocomplete="off" bind:value={name} class="input" id="name" type="text" />
        <button class="btn" on:click={greet}>Greet</button>
    </div>
{:else if page == 1}
    <p>Hi from page 1</p>
{:else}
    <p>Unknown page</p>
{/if}

<style>
</style>
