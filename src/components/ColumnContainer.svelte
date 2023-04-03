<script>

    export let row;

</script>

<div class="column" style="{'grid-column: 2/4; grid-row:' + row + "/" + row}">
    <slot></slot>
</div>

<style>
    .column   {
        display: flex;
        flex-direction: row;
        gap: 10px;
        width: 100%;
    }

    .column  :global(*) {
        min-width: 0;
        flex: 1;
    }

    @media only screen and (max-width: 800px) {
		.column  {
            flex-direction: column;
        }
	}
</style>