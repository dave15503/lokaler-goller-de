<script>

    export let menues;

    let windowHeight = window.innerHeight;
    let bannerHeight, menuHeight;

    if (window.innerWidth < 800) {
        bannerHeight = 0.7 * windowHeight;
        menuHeight = windowHeight - bannerHeight;
    } else {
        bannerHeight = 0.9 * windowHeight;
        menuHeight = windowHeight - bannerHeight;
    }

    window.onresize= (evt) => {
        windowHeight = window.innerHeight;

        // check for mobile screen width
        if (window.innerWidth < 800) {
            bannerHeight = 0.75 * windowHeight;
            menuHeight = windowHeight - bannerHeight;
        } else {
            bannerHeight = 0.9 * windowHeight;
            menuHeight = windowHeight - bannerHeight;
        }
    };

    function scrollTo(href) {
        const element = document.querySelector(href);
        console.log(element)
        const position = element.getBoundingClientRect().top + window.pageYOffset - menuHeight;

        console.log("scrolling to " + position + " of " + JSON.stringify(element));

        window.scrollTo({
            top: position,
            baviour: "smooth"
        });

    }
</script>

<span class="landing-page">
    <div class="banner" style="height: {bannerHeight}px;">
        <div class="logo">
            <h1>LOKALER GOLLER</h1>
            <h2>
                Ihre freundliche und professionelle Andachtsstätte in der
                Nachbarschaft.
            </h2>
        </div>

        <div class="menu socials">
            <a class="link" href="/">
                <img
                    src="./assets/instagram.png"
                    alt="InstagramIcon"
                    width="25px"
                    height="25px"
                />
            </a>
            <a class="link" href="https://goo.gl/maps/oKvgYZV2cxYM84RW7">
                <img
                    src="./assets/googlemaps.png"
                    alt="GoogleMapsIcon"
                    width="25px"
                    height="25px"
                />
            </a>
        </div>
    </div>

    <div class="menubar" style="height: {menuHeight}px; --menu-height: {menuHeight}px;">
        <div class="menu main">
            {#each menues as menu (menu.id)}
                <div class="element link" on:click={(evt) => scrollTo(menu.link)}>
                    {menu.title}
                </div>
            {/each}
        </div>
        
    </div>
</span>

<style>
    .landing-page {
        --banner-height: 0.9;
    }

    .menubar {
        background-color: var(--background-color);

        position: sticky;
        top: 0;
    }

    .banner {
        font-weight: 100;

        background-image: url("../assets/gmapsImage.jpg");
        background-repeat: repeat-x;
        background-size: contain;
        background-position: center center;

        padding: 0;
        position: relative;
    }

    .menu {
        display: flex;
        align-items: center;
        flex-direction: row;
        justify-content: center;
        gap: 50px;
        padding: 5px;

        font-size: var(--headline-font-size);
    }

    .socials {
        position: absolute;
        right: 0;
        bottom: 0;
        float: right;
    }

    .logo {
        text-align: center;
        position: absolute;
        left: 50%;
        top: 40%;
        transform: translate(-50%,-40%);

        font-weight: 300;
    }

    .logo h2 {
        font-weight: 200;
        font-size: var(--subheadline-font-size);
    }

    .logo h1 {
        font-size: var(--title-font-size);
    }


    @media only screen and (max-width: 800px) {
        .main.menu {
            flex-flow: column;
            gap: 5px;
        }

        .menu {
            font-size: calc(var(--menu-height) / 6);
        }
    }
</style>
