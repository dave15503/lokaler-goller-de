<script>
    let menues = [
        { id: 0, title: "Home", link: "" },
        { id: 1, title: "Contact", link: "" },
        { id: 2, title: "Impressum", link: "" },
    ];

    function onSelectTab(id) {}
</script>

<span class="head">
    <div class="headline">
        <div class="logo">
            <div>
                LOKALER GOLLER
            </div>
            <div class="sublogo">
                Ihre freundliche und professionelle Andachtsstätte in der Nachbarschaft.
            </div>
        </div>
        <div class="socials">
            <a href="/">
                <img src="./assets/instagram.png" alt="InstagramIcon" width="25px" height="25px"/>
            </a>
            <a href="https://goo.gl/maps/oKvgYZV2cxYM84RW7">
                <img src="./assets/googlemaps.png" alt="GoogleMapsIcon" width="25px" height="25px"/>
            </a>
        </div>
    </div>

    <div class="menu">
        {#each menues as menu (menu.id)}
            <a href={menu.link} class="element" on:click={(evt) => onSelectTab(menu.id)}>
                {menu.title}
            </a>
        {/each}
    </div>
</span>

<style>

    .head {
        grid-column: 1/4;
        grid-row: 1/1;

        height: 100vh;
        width: 100vw;
    }

    .menu {
        height: 10vh;
        display: flex;
        align-items: center;
        flex-direction: row;
        justify-content: center;
        gap: 50px;
    }

    .headline {
        font-size: 56px;
        font-weight: 100;

        background-image: url(https://lh5.googleusercontent.com/p/AF1QipP0x7Db83nsP6wJK-MEhslEfff1QgcICu5FHGBR=w203-h270-k-no);
        background-repeat: repeat-x;
        background-size: contain;
        background-position: center center;

        padding: 0;
        height: 90vh;
    }

    .logo{
        text-align: center;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

        font-weight: 300;
    }

    .sublogo {
        font-weight: 200;
        font-size: var(--subheadline-font-size);
    }

    .socials {
        position: absolute;
        bottom: 10%;
        right: 10%;

        display: flex;
        flex-flow: row-reverse;
    }

    .element {
        font-size: var(--headline-font-size);
    }
</style>
