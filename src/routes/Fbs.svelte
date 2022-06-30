<script>
    import MenuBar from "../components/MenuBar.svelte";
    import SectionContainer from "../components/SectionContainer.svelte";
    import SectionHeadline from "../components/SectionHeadline.svelte"

    let menuItems = [
        { id: 0, title: "Erfolge", link: "#erfolge" },
        { id: 1, title: "Fusball", link: "#fussball" },
        { id: 2, title: "Esport", link: "#esport" },
        { id: 3, title: "Vereinslokal: Lokaler Goller", link: "/"}
    ];

</script>


<MenuBar {menuItems} title="Fenerbahçe Schnad ev. 2021"></MenuBar>


<div class="banner">
</div>
<div class="logo">
    <h1>
        Willkommen bei der Fenerbahçe Schnad
    </h1>
    <h2>
        Traditions- Fußball und E-Sport Club aus Wolfersgrün City seit 2018
    </h2>
</div>

<div class="content-grid">
    <SectionHeadline row="1" tag="staff" headline="Das Team" subheadline="der FbS"></SectionHeadline>
    <SectionContainer row="2" orientation="right" minHeight="300" imagePath="../assets/fbs/Gico_Noller_2.jpg">
        <h1 slot="section-headline">
            El Presidente 
        </h1>
        <section slot="section-content">
            <h2>
                Gico Noller
            </h2>
            <p>
                Seit Beginn leidentschaftlich engagiert
                <br>
                Professioneller Türke und Shishabarbetreiber
            </p>
        </section>
        
    </SectionContainer>


</div>


<div class="about">
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

        background-image: url(../assets/fbs/Fenerbahce_Schnad_Esports.png);
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

    .about {
        text-align: center;
    }

    @media only screen and (max-width: 800px) {
        .banner {
            background-size: contain;
        }

        .content-grid {
			/* Mobile page changes the grid to a flex column.
			Requires no change in the childs columns as they just ignore them when the parent is a flex*/
			display: flex;
			flex-direction: column;
			padding-left: 15px;
			padding-right: 15px;

		}
    }

    .content-grid {
		display: grid;
		justify-content: center;
		justify-items: center;
		grid-template-columns: 20% minmax(200px, 30%) minmax(200px, 30%) 20%;
		grid-template-rows: repeat(5, auto);
        row-gap: 20px;
        margin-top: 20px;

	}

</style>