<script>
    import { fade} from 'svelte/transition';
    // Array of {path: '', alt: ''} objects
    // to render side by side and scroll through from time to time
    export let imagesList;

    export let row;

    let currentIndex = 0;
    let prevIdx = 0;

    const goLeft = () => {
        if(currentIndex > 0){
            currentIndex -= 1;
        }
    }

    const goRight = () => {
        if(currentIndex < imagesList.length - 1){
            currentIndex += 1;
        }
    }

    const setIndex = (idx) => {
        currentIndex = idx;
    }

</script>

{#if imagesList != null && imagesList.length > 0}
    <div class="image-container" style={"grid-row:" + row + "/" + row + ";"}>
        <div class="image-controls">
            <div class="arr-l" on:click={goLeft}>
                &lsaquo
            </div>
            <div class="image-progress-bar">
                {#each imagesList as dot, index}
                    {#if index == currentIndex}
                        <span class="pb-item highlighted" ></span>
                    {:else}
                        <span class="pb-item" on:click={() => setIndex(index)}></span>
                    {/if}
                {/each}
            </div>
            <div class="arr-r" on:click={goRight}>
                &rsaquo
            </div>
        </div>
        {#key currentIndex}
            <div transition:fade={{duration: 500}} class="image-view" style={ "background-image: " + imagesList[currentIndex].content + ";"}></div>
        {/key}


    </div>
{:else}
    <div class="image-container" style="grid-row: {row}\{row}">
        <i>
            No images to load!
        </i>
    </div>
{/if}

<style>

    .image-view {
        position: absolute;
        background-size: contain;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        height: 100%;
        z-index: 0
    }

    .image-container {
        width: 100%;
        grid-column: 2/4;
        height: 500px;
        position: relative;
        overflow: hidden;
        margin-top: 5px;
        margin-bottom: 5px;
    }

    .image-controls {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        height: 100%;
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        z-index: 1;
        background-color: transparent;
        user-select: none;
        /*background-color: rgba(0, 0, 0, 0);*/
    }

    .image-controls > * {
        opacity: 0;
        transition: opacity 500ms;
    }

    .image-controls:hover > * {
        opacity: 1;
    }

    .image-progress-bar {
        align-self: flex-end;
        text-align: center;
        margin-bottom: 15px;
        flex-grow: 1000;
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: calc(var(--subheadline-font-size)/3);
        overflow: hidden;
    }

    .pb-item {
        border-radius: 50%;
        background-color: var(--secondary-background-color);
        width: var(--text-font-size);
        height: var(--text-font-size);
        display: inline-block;
        cursor: pointer;
    }

    .pb-item.highlighted{
        background-color: var(--secondary-text-color);
        width: calc(var(--text-font-size)*1.2);
        height: calc(var(--text-font-size)*1.2);
    }

    .arr-l , .arr-r {
        cursor: pointer;
        font-size: var(--title-font-size);
        padding: 5px;
        padding-top: 30px;
        padding-bottom: 30px;
        background-color: rgba(255, 255, 255, 0.1);
    }

    .arr-l {
        border-top-right-radius: 1000px;
        border-bottom-right-radius: 1000px;
    }

    .arr-r {
        border-top-left-radius: 1000px;
        border-bottom-left-radius: 1000px;
    }

</style>