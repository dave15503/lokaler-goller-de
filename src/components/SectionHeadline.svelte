<script>
    export let row;
    export let tag;
    export let headline;
    export let subheadline;
</script>


<div class="container" id={tag} style={"grid-row: "+ row + "/" + row}>
    <h1>{headline}</h1>
    {#if subheadline != null}
        <h2>{subheadline}</h2>
    {/if}
</div>

<style>
    .container {
        text-align: center;
        grid-column: 2/4;
    }
</style>