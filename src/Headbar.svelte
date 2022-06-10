<script>
    export let menues;

    let menuOpen = false;

    function scrollTo(href) {
        const element = document.querySelector(href);
        console.log(element);

        const menu = document.querySelector("#menu");

        const position = element.getBoundingClientRect().top + window.pageYOffset - menu.offsetHeight;

        console.log("scrolling to " + position + " of " + JSON.stringify(element));

        window.scrollTo({
            top: position,
            baviour: "smooth",
        });
    }
</script>

<span class="landing-page" id="start">
    <div class="top-nav" id="menu">
        <div class="nav">
            <h1 class="top-nav-wrap">
                <a href="#start"> Lokaler Goller </a>
            </h1>
            <span class="top-nav-main nav">
                {#each menues as menu (menu.id)}
                    <div class="link" on:click={(evt) => scrollTo(menu.link)}>
                        {menu.title}
                    </div>
                {/each}
            </span>
            <div class="hamburger-menu {menuOpen ? 'active' : ''}" on:click={(evt) => (menuOpen = !menuOpen)}>
                <div />
            </div>
        </div>
        <div class="top-nav-main-vertical {menuOpen ? 'active' : ''}">
            {#each menues as menu (menu.id)}
                <div class="link" on:click={(evt) => scrollTo(menu.link)}>
                    {menu.title}
                </div>
            {/each}
        </div>
    </div>

    <div class="banner">
        <div class="logo">
            <h1>LOKALER GOLLER</h1>
            <h2>Ihre freundliche und professionelle Andachtsstätte in der Nachbarschaft.</h2>

            <div class="nav socials">
                <a class="link" href="/">
                    <img src="./assets/instagram.png" alt="InstagramIcon" width="25px" height="25px" />
                </a>
                <a class="link" href="https://goo.gl/maps/oKvgYZV2cxYM84RW7">
                    <img src="./assets/googlemaps.png" alt="GoogleMapsIcon" width="25px" height="25px" />
                </a>
                <a class="link" href="https://github.com/dave15503/lokaler-goller-de">
                    <img src="./assets/GitHubMark.png" alt="GithubImage" width="25px" height="25px"/>
                </a>
            </div>
        </div>
    </div>
</span>

<style>
    .landing-page {
        width: 100%;
        display: inline-block;
        height: 100vh;
    }

    .nav {
        display: flex;
        flex-direction: row;
        align-items: center;
    }

    .top-nav-wrap {
        font-size: var(--headline-font-size);
        padding-right: 50px;
        padding-left: 30px;
        margin-top: 5px;
        margin-bottom: 5px;
    }

    .top-nav-main {
        gap: 25px;
        font-size: var(--subheadline-font-size);
    }

    .top-nav {
        position: fixed;
        z-index: 10;
        background-color: var(--background-color);
        width: 100%;
    }

    .banner {
        height: 100%;

        background-image: url("../assets/gmapsImage.jpg");
        background-repeat: repeat-x;
        background-size: contain;
        background-position: center center;
        position: relative;
        padding-right: 20px;
        padding-left: 20px;
        display: flex;
        justify-content: center;
        align-items: center;



    }

    @keyframes slideUp {
        0% {
            transform: translateY(75px); 
        }
        100% {
            transform: translateY(0);
        }
    }

    .logo {
        text-align: center;
        font-weight: 100;


    }

    .socials {
        justify-content: center;
        gap: 20px;
        margin-top: 20px;
        animation: 0.8s ease-out 0s 1 slideUp;
    }

    .logo h1 {
        font-size: var(--title-font-size);
        animation: 0.4s ease-out 0s 1 slideUp;
    }

    .logo h2 {
        animation: 0.6s ease-out 0s 1 slideUp;
    }

    .hamburger-menu {
        display: none;
        justify-self: end;

        height: 40px;
        width: 40px;

        align-items: center;
        justify-content: center;
    }

    .hamburger-menu > div {
        position: relative;
        top: 0;
        left: 0;
        background: white;
        height: 2px;
        width: 60%;
        transition: all 0.5s ease-in-out;
    }

    .hamburger-menu > div::before,
    .hamburger-menu > div::after {
        content: "";
        position: absolute;
        top: -10px;
        background: white;
        width: 100%;
        height: 2px;
        transition: all 0.5s ease-in-out;
    }

    .hamburger-menu > div::after {
        top: 10px;
    }

    .hamburger-menu.active > div::before {
        transform: rotate(45deg);
        top: 0;
        background: white;
    }
    .hamburger-menu.active > div::after {
        transform: rotate(-45deg);
        top: 0px;
        background: white;
    }

    .hamburger-menu.active > div {
        background: rgba(0, 0, 0, 0);
    }

    .top-nav-main-vertical {
        display: flex;
        overflow: hidden;
        flex-direction: column;
        align-items: center;
        padding-bottom: 5px;
        gap: 5px;
        font-size: var(--subheadline-font-size);
        max-height: 0px;
        transition: max-height 0.5s ease-out;
    }

    @media only screen and (max-width: 800px) {
        .hamburger-menu {
            display: flex;
        }

        .top-nav-main {
            display: none;
        }

        .top-nav > .nav {
            justify-content: space-between;
        }

        .top-nav-main-vertical.active {
            display: flex;
            max-height: 500px;
        }
    }
</style>
