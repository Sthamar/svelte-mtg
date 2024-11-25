<script>
    export let score;
    export let winningText;
    export let won;
    export let fontColor;
    export let gameOver = false;

    function plusOne(){
        score = score + 1
    }
    function minusOne(){
        score = score - 1
    }

</script>

<style>
    .player{
        flex-grow: 1;

    }
    .plus{
        background-color: seagreen;
    }
    .minus{
        background-color: brown;
    }
    button[disabled]{
        background-color: gray;
        pointer-events: none;
    }
    button{
        font-size: 20px;
        border-radius: 3px;
        width: 40px;
        color:white;
        font-family: monospace;
        font-weight: bold;
    }
</style>

<div class="player" style="color:{fontColor}">
    <h2>{score}</h2>
    <button disabled={gameOver} on:click={plusOne} class="plus">+</button>
    <button disabled={gameOver} on:click={minusOne} class="minus">-</button>
    {#if won}
        <h2>{winningText}</h2>
    {/if}
    
</div>