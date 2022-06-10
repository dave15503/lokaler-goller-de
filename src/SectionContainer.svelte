<script>
    // container that displays a text content and an background image
    // should be utilized for more generic information
    // the most prominent parts of the page will get their own animated containers

    export let imagePath;
    export let orientation;
    export let tag; // id for the scrolling
    export let row;

    $: orientationOpposite = orientation == "left" ? "right" : "left";

</script>

<div class={"image " + orientationOpposite} style={"grid-row: " + row + "/" + row + "; background-image: url(" + imagePath + "),  linear-gradient(green, violet)"}>
    **Placeholder**
</div>
<div class={"content " + orientation} id={tag} style={"grid-row: " + row + "/" + row + ";"}>
    <slot></slot>
</div>


<style>

    .content {
        padding: 20px;
    }

    .image {
        height: 100%;
        width: 100%;
        min-height: 500px;
    }

    .left.image {
        grid-column: 2/3;
    }

    .right.image{
        grid-column: 3/4;
    }

    .right.content {
        grid-column: 3/4;
    }

    .left.content {
        grid-column: 2/3;
    }



</style>
