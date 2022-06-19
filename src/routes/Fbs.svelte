<script>
    import MenuBar from "../components/MenuBar.svelte";

    let menuItems = [
        { id: 0, title: "Erfolge", link: "#erfolge" },
        { id: 1, title: "Fusball", link: "#fussball" },
        { id: 2, title: "Esport", link: "#esport" },
        { id: 3, title: "Vereinslokal: Lokaler Goller", link: "/"}
    ];

</script>


<MenuBar {menuItems} title="Fenerbahçe Schnaad ev. 2021"></MenuBar>


<div class="banner">
</div>
<div class="logo">
    <h1>
        Willkommen bei der Fenerbahçe Schnaad
    </h1>
    <h2>
        Traditions- Fußball und E-Sport Club aus Wolfersgrün City
    </h2>
</div>

<div>
    Disclaimer: Scherz, kein Angemeldeter Verein
    <br>
    Anständiges Impressum folgt später, diese Website ist in der Entwicklungsphase
    <br>
    Warum ich auf dem production server entwickle? Weil ich kann.
</div>

<style>
    .banner {
        width: 100%;
        height: 70vh;

        background-image: url(../assets/Fenerbahce_Schnad_Esports.png);
        background-repeat: no-repeat;
        background-size: 50vh;
        background-position: center center;
    }

    .logo {
        text-align: center;
    }
    .logo h1 {
        font-size: var(--title-font-size);
        animation: 0.4s ease-out 0s 1 slideUp;
    }

    .logo h2 {
        animation: 0.6s ease-out 0s 1 slideUp;
    }

    @media only screen and (max-width: 800px) {
        .banner {
            background-size: contain;
        }
    }
</style>