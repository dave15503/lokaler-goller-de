<script>
    let menues = [
        { id: 0, title: "Das Lokal", link: "#bar" },
        { id: 1, title: "Gastgeber", link: "#host" },
        { id: 2, title: "Impressum", link: "#about" },
    ];

    function onSelectTab(id) {}
</script>

<span class="head">
    <div class="headline">
        <div class="logo">
            <div style="font-size: 56px;">
                LOKALER GOLLER
            </div>
            <div class="sublogo">
                Ihre freundliche und professionelle Andachtsstätte in der Nachbarschaft.
            </div>
        </div>

    </div>


    <div class="menubar">
        <div class="menu">
        {#each menues as menu (menu.id)}
            <a href={menu.link} class="element" on:click={(evt) => onSelectTab(menu.id)}>
                {menu.title}
            </a>
        {/each}

        </div>
        <div class="menu">
            <a href="/">
                <img src="./assets/instagram.png" alt="InstagramIcon" width="25px" height="25px"/>
            </a>
            <a href="https://goo.gl/maps/oKvgYZV2cxYM84RW7">
                <img src="./assets/googlemaps.png" alt="GoogleMapsIcon" width="25px" height="25px"/>
            </a>
        </div>
    </div>


</span>

<style>

    .head {
        grid-column: 1/5;
        grid-row: 1/1;

        height: 100vh;
        width: 100vw;
    }

    .menubar {
        background-color: var(--background-color);

        position: sticky;
        top: 0;
        height: 10vh;
    }

    .menu {

        display: flex;
        align-items: center;
        flex-direction: row;
        justify-content: center;
        gap: 50px;
        padding: 5px;


    }

    .headline {

        font-weight: 100;

        background-image: url(https://lh5.googleusercontent.com/p/AF1QipP0x7Db83nsP6wJK-MEhslEfff1QgcICu5FHGBR=w203-h270-k-no);
        background-repeat: repeat-x;
        background-size: contain;
        background-position: center center;

        padding: 0;
        height: 90vh;

        display: flex;
        align-items: center;
        justify-items: center;
        justify-content: center;
        flex-direction: column;
    }

    .logo{
        text-align: center;
        position: relative;


        font-weight: 300;
    }

    .sublogo {
        font-weight: 200;
        font-size: var(--subheadline-font-size);
    }


    .element {
        font-size: var(--headline-font-size);
    }
</style>
