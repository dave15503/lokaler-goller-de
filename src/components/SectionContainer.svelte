<script>
    // container that displays a text content and an background image
    // should be utilized for more generic information
    // the most prominent parts of the page will get their own animated containers
    import { fly } from "svelte/transition";
    import { onMount } from "svelte";

    export let imagePath;
    export let orientation;
    export let tag; // id for the scrolling
    export let row;
    export let minHeight = -1;
    export let imageSubtitle = "";

    let scrolledIntoContent = false;

    $: orientationOpposite = orientation == "left" ? "right" : "left";

    let observer;

    onMount(async () => {
        observer = new IntersectionObserver((entries) => {
            entries.forEach((entry) => {
                console.log(entry.isIntersecting + " observed in row " + row)
                if (entry.isIntersecting) {
                    scrolledIntoContent = true;
                    return
                }
                scrolledIntoContent = false;
            });
        });
        let hdl = document.querySelector("#section-headline-" + row);
        console.log(hdl);
        observer.observe(hdl);
        //observer.observe(document.querySelector("section-content-" + row))
    });
</script>

<div class="{'image ' + orientationOpposite}" style={'grid-row: ' + row + '/' + row + '; background-image: url(' + imagePath + ") " + (imagePath !== "" ? ";" : (",  linear-gradient(green, violet);")) + (minHeight > 0 ? "height: " + minHeight + "px;" : "")}>
    {#if imageSubtitle != ""}
        <div class="image-subtitle">{imageSubtitle}</div>
    {/if}
</div>
<div class="{'content ' + orientation}" id="{tag}" style="{'grid-row: ' + row + '/' + row + ';'}">
    {#key scrolledIntoContent}
        <div id="{'section-headline-' + row}" in:fly="{{ x: 0, y: -30, duration: 1000, delay: 200 }}">
            <slot name="section-headline">
                <h1>Default Headline</h1>
            </slot>
        </div>
        <div id="{'section-content-' + row}" in:fly="{{ x: orientation === 'left' ? -100 : 100, y: 0, duration: 1000, delay: 200 }}">
            <slot name="section-content">
                <h2>Lorem Ipsum</h2>
                <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras sagittis quam condimentum, commodo neque vitae, mattis odio. Vestibulum sit amet commodo sapien. Mauris egestas vehicula luctus. Vivamus pulvinar vitae elit eu tempor. Proin congue sem feugiat mauris hendrerit dictum. Aenean lacus lorem, facilisis cursus quam quis, egestas ultrices mi. Sed dapibus magna ac leo pharetra, quis gravida magna tristique. Nunc ac tincidunt dolor , non sagittis nisi. Aenean condimentum, neque et hendrerit egestas, massa ligula aliquam nunc, fermentum ultricies nisi ante nec neque. Proin felis nisi, convallis quis ex eget, venenatis suscipit risus. Aenean pharetra orci eu turpis sagittis dignissim. Phasellus sapien lorem, dignissim vitae mollis eu, aliquet vitae augue. Duis fringilla elit nulla, a mattis lacus euismod vitae. Suspendisse potenti. Sed sapien orci, facilisis quis mauris vitae, pharetra rutrum quam. Nunc volutpat tincidunt cursus.</p>
            </slot>
        </div>
    {/key}
</div>

<style>
    .content {
        padding: 20px;
    }

    .image {
        display: inline-block;
        position: relative;
        height: 100%;
        width: 100%;
        background-size: contain;
        background-repeat: no-repeat;
        background-position: center, center;
    }

    .image-subtitle {
        position: absolute;
        bottom: 0;
        width: 100%;
        font-size: var(--minor-font-size);
        color: var(--secondary-text-color);
    }

    .left.image {
        grid-column: 2/3;
    }

    .right.image {
        grid-column: 3/4;
    }

    .right.content {
        grid-column: 3/4;
    }

    .left.content {
        grid-column: 2/3;
    }

    @media only screen and (max-width: 800px) {
        .image {
            min-height: 400px;
        }
    }
</style>
