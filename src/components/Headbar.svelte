<script>
    import MenuBar from "./MenuBar.svelte"

    export let menuItems;



</script>

<span class="landing-page" id="start">
   <MenuBar {menuItems} title="Lokaler Goller" ></MenuBar>

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


</style>
