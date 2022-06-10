<script>

    // Array of {path: '', alt: ''} objects
    // to render side by side and scroll through from time to time
    export let imagesList = [];

    export let row;

    let currentIndex = 0;

</script>

{#if imagesList != null}
    <div class="image-container" style="grid-row: {row}\{row}">
        <div class="image-controls">
            <div class="arr-l">
                >
            </div>
            <div class="image-progress-bar">
                +++++++
            </div>
            <div class="arr-r">
                =>
            </div>
           
        </div>
    </div>
{:else}
    <div class="image-container" style="grid-row: {row}\{row}">
        <i>
            No images to load!
        </i>
    </div>
{/if}

<style>
    .image-container {
        width: 100%;
        grid-column: 2/4;
        height: 500px;
    }

    .image-controls {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        height: 100%;
        /*background-color: rgba(0, 0, 0, 0);*/
    }

    .image-controls > * {
        visibility: hidden;
    }

    .image-controls:hover > * {
        visibility: visible;
    }

    .image-progress-bar {
        align-self: flex-end;
        text-align: center;
        margin-bottom: 15px;
        flex-grow: 1000;
    }

    .arr-l , .arr-r {
        cursor: pointer;
    }

</style>