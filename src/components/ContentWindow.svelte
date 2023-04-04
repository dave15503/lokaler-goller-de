<script>

</script>

<div class="container">
    <div class="content">
        <slot name="text"></slot>
    </div>
    <div class="image">
        <slot name="image"></slot>
    </div>
</div>

<style>

    .container {
        position: relative;
        display: inline-block;
        overflow: hidden;
    }
    .content, .image {
        width: 100%;
        height: 100%;
    }

    .image {
        position: relative;
        z-index: 0;
        top: 0;
    }
    
    .image :global(img) {
        max-width: 100%;
        height: 100%;
        max-height: 600px;
    }
    
    .content {
        position: absolute;
        z-index: 1;
        color: var(--text-color);
        transform: translateY(100%);

        transition: transform 0.5s ease, background-color 0.5s ease;
    }


    .container:hover .content {
        transform: translate(0%);
        background-color: rgba(0,0,0,0.5);
    }
    
   



</style>