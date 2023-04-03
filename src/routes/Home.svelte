<script>
	import Headbar from "../components/Headbar.svelte";
	import About from "../components/About.svelte";
	import ImageScroller from "../components/ImageScroller.svelte";
	import SectionContainer from "../components/SectionContainer.svelte";
	import ColumnContainer from "../components/ColumnContainer.svelte";
    import SectionHeadline from "../components/SectionHeadline.svelte";

	let menuItems = [
		{ id: 0, title: "Das Lokal", link: "#bar" },
		{ id: 1, title: "Gastgeber", link: "#host" },
		{ id: 2, title: "Impressum", link: "#about" },
		{ id: 3, title: "Fbs", link: "/fbs" },
	];

	let scroller0ImgList = [
		{ alt: "Image 0", content: "linear-gradient(red, violet)" },
		{ alt: "Image 1", content: "linear-gradient(blue, red)" },
		{ alt: "Image 2", content: "linear-gradient(green, yellow)" },
	];
</script>

<main>
	<Headbar {menuItems} />

	<div class="content-grid">
		<SectionContainer
			orientation="right"
			tag="bar"
			imagePath="/assets/lg_2.png"
			row="1"
		>
			<h1 slot="section-headline">Das Lokal</h1>
			<section slot="section-content">
				<p>
					Der Lokale Goller lädt regelmäßig zum Entspannen in ruhiger
					und relaxter Atmosphäre ein. Im urigen Dämmerschein der Andachtsstätte
					wird hier im kleinen Kreise die heilige Blubbermaschine verehrt.
				</p>
				<p>
					Im süßlichen duft der Shish kommt die Gesellschaftlichkeit nie zu kurz.
					Zwischen einer Exzellenten Auswahl an Getränken und Speisen lockt eine
					Vielzahl an Angeboten wie die Musikanlage, Beerpontisch und regelmäßiger
					Übertragung der Höchstklassigsten Sportevents.
				</p>
					
				<p>
					Ob als einfache Shishabar oder Austragungsstätte größerer Events,
					der Lokale Goller ist für jedes Veranstaltung die perfekte Location.
				</p>
			</section>
		</SectionContainer>

		<ImageScroller row="2" imagesList={scroller0ImgList} />

		<SectionContainer orientation="left" tag="host" imagePath="" row="3">
			<div slot="section-headline">
				<h1>Ihre Gastgeber</h1>
			</div>

			<section slot="section-content">
				<h2>Gico Noller</h2>
				<p>
					Türkischster Shishabar-Inhaber der nördlichen Hemisphäre
				</p>
				<h2>
					Prof. der Shishalogie und staatl. anerkanner Blubbermeister
					"Zimt" Wundrich
				</h2>
				<p>
					Schon seit Kindesalter erfahren und versiert im Umgang mit Tabak
					und allen anderen Arten von Räucherwerk.
				</p>
				<h2>
					Der Bierpongdieter
				</h2>
				<p>
					Ist weder Teil des Personals, noch eingeladen,
					aber doch immer am Start
				</p>
			</section>
		</SectionContainer>

		<SectionContainer tag="activities">
			<div slot="section-headline"></div>
		</SectionContainer>

		<About></About>
	</div>
</main>

<style>
	.content-grid {
		display: grid;
		justify-content: center;
		justify-items: center;
		grid-template-columns: 20% minmax(200px, 30%) minmax(200px, 30%) 20%;
		grid-template-rows: repeat(5, auto);
	}

	@media only screen and (max-width: 800px) {
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
