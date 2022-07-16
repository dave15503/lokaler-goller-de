<script>
    import MenuBar from "../components/MenuBar.svelte";
    import SectionContainer from "../components/SectionContainer.svelte";
    import SectionHeadline from "../components/SectionHeadline.svelte"

    let menuItems = [
        { id: 0, title: "Geschichte", link: "#history" },
        { id: 1, title: "Fusball", link: "#soccer" },
        { id: 2, title: "Esport", link: "#esport" },
        { id: 3, title: "Vereinslokal", link: "/"}
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
    <SectionHeadline row="1" tag="history" headline="Vereinsgeschichte"></SectionHeadline>

    <SectionContainer row="2" orientation="left" imagePath="../assets/fbs/Gruppenfoto.png">
        <h2 slot="section-headline">
            Die Fenerbahçe Schnad
        </h2>
        <section slot="section-content">
            <p>
                Sportliche Höchstleistung, Leidenschaft und Tradition - Dafür stehen wir mit unserem Namen!
            </p>
            <p>
                Seit 2018 im wunderschönen Wolfersgrün die Vereinsgründung besiegelt wurde,
                durchlebte die Fenerbahçe Schnad eine turbulente Vereinsgeschichte,
                von großen Siegen, Freudentränen und Niederlagen.
            </p>
            <p>
                kein plan man, das soll wer anders schreiben lol.
            </p>
            <p>
                TODO: leute nach einwilligung fragen bevor die Bilder hier landen... also erstmal verpixelt
            </p>
        </section>
    </SectionContainer>

    <SectionHeadline row="5" tag="soccer" headline="Fußball"></SectionHeadline>
    <SectionContainer row="6" orientation="right">
        <h2 slot="section-headline">
            Die wildesten Busfahrer im Oberland
        </h2>
        <section slot="section-content">
            <p>
                Hier bitte text über Fußball und so, ne? Alles klar danke!
            </p>
        </section>
    </SectionContainer>

    <SectionHeadline row="10" tag="esport" headline="Esport"></SectionHeadline>
    <SectionContainer row="11" orientation="left">
        <h2 slot="section-headline">
            Die Fenerbahçe hinter dem Monitor.
        </h2>
        <section slot="section-content">
            <p>
                Nicht nur auf dem Rasen sondern auch vor der Tastatur ist Schnad aktiv!
                <br>
                Im  Januar 2021 wurde der Verein um eine E-Sport Sparte erweitert die prompt
                und wie von der Fenerbahçe erwartet große Erfolge verzeichnen konnte.
                <br>
                In professionellen Umfeld verteidigen wir die Ehre des Oberlandes auch im
                Digitalen Strafraum in einer Vielzahl von Spielen:
            </p>
        </section>
    </SectionContainer>
    <SectionContainer row="12" orientation="right">
        <h2 slot="section-headline">
            League of Legends
        </h2>
        <section slot="section-content">
            <p>
                League of Legends ist ein Massive-Multiplayer Online Battle Arena Spiel in dem
                es darum geht den mentalen Zerfall in der Kluft zu überleben.
            </p>
            <p>
                Dabei geht es vorraning darum, ruhig zu bleiben wenn die Teammates zum wiederholten
                Mal sich in den Freitod stürzen und dem wagemutigen Spieler über die Textnachrichten
                Todeswünsche zukommen lassen
            </p>
            <p>
                Yeah... s'pose that sums it up pretty accurately
            </p>

        </section>
    </SectionContainer>


    <SectionHeadline row="20" tag="staff" headline="Die Vorstandschaft" subheadline="der FbS"></SectionHeadline>
    <SectionContainer row="21" orientation="right" minHeight="300" imagePath="../assets/fbs/Gico_Noller_2.jpg">
        <h1 slot="section-headline">
            Vereinspräsident
        </h1>
        <section slot="section-content">
            <h2>
                Gico Noller
            </h2>
            <p>
                Gründungsmitglied
                <br>
                Organisator und Leiter des Vereinslokals
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

    .content-grid {
		display: grid;
		justify-content: center;
		justify-items: center;
		grid-template-columns: 20% minmax(200px, 30%) minmax(200px, 30%) 20%;
		grid-template-rows: repeat(5, auto);
        row-gap: 20px;
        margin-top: 20px;

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

</style>