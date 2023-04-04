<script>
	import Headbar from "../components/Headbar.svelte";
	import About from "../components/About.svelte";
	import ImageScroller from "../components/ImageScroller.svelte";
	import SectionContainer from "../components/SectionContainer.svelte";
	import ColumnContainer from "../components/ColumnContainer.svelte";
    import SectionHeadline from "../components/SectionHeadline.svelte";
    import ContentWindow from "../components/ContentWindow.svelte";

	let menuItems = [
		{ id: 0, title: "Das Lokal", link: "#bar" },
		{ id: 1, title: "Gastgeber", link: "#host" },
		{ id: 2, title: "Aktivitäten", link: "#activities"},
		{ id: 3, title: "Ausstattung", link: "#equipment"},
		{ id: 4, title: "Impressum", link: "#about" },
		{ id: 5, title: "Fbs", link: "/fbs" },
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


		<SectionContainer orientation="left" tag="host" imagePath="/assets/rotlicht.jpg" row="3">
			<div slot="section-headline">
				<h1>Ihre Gastgeber</h1>
			</div>

			<section slot="section-content">
				<h2>Gico Noller</h2>
				<p>
					Türkischster Shishabar-Inhaber der nördlichen Hemisphäre
				</p>
				<h2>
					Prof. der Shishalogie und staatl. anerkannter Blubbermeister
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

		<SectionContainer tag="activities" orientation="right" row="4" imagePath="/assets/vitrine.jpg">
			<div slot="section-headline">
				<h1>	
					Aktivitäten
				</h1>
			</div>
			<section slot="section-content">
				<p>
					Von schlichtem Blubbern, massenhaftem Alkoholkonsum über Beerpong bis zu Karaoke,
					hat der Lokale Goller viel zu bieten. Zu jedem Zeitpunkt lädt die große
					Auswahl an (nicht)alkoholischen Getränken dazu ein, ein paar Gehirnzellen zu ermorden,
					und dabei etwas von der großen Zahl verfügbarer Snacks zu genießen.
				</p>
				<p>
					Doch neben dem Lokal-Betrieb bildet der Lokale Goller auch das Stammlokal für den weltbekannten
					Traditionsverein Fenerbaçe Schnaad.
				</p>
			</section>
		</SectionContainer>

		<SectionContainer tag="equipment" orientation="left" row="5" imagePath="/assets/shish.jpg">
			<div slot="section-headline">
				<h1>
					Ausstattung
				</h1>
			</div>
			<div slot="section-content">
				<ul>
					<li>
						Blubbermaschine mit 4 Anschlüssen und 3 Schläuchen
					</li>
					<li>
						Nitendeo Switch
					</li>
					<li>
						Hightech-PC
					</li>
					<li>
						LED-Blinkmaschine
					</li>
					<li>
						69.420 Watt Soundanlage und feinster Musikgeschmack
					</li>
					<li>
						Professioneller Beerpong-Tapeziertisch
					</li>
					<li>
						Gesellschaftsspiele aller Art
					</li>
					<li>
						Palmen für Urlaubsfeeling - Auch im Winter
					</li>
				</ul>
			</div>
		</SectionContainer>

		<ColumnContainer row="6">
			<ContentWindow>
				<div slot="text" class="content-window-text">
					<h3>Hightech PC</h3>
					<p>
						Mithilfe überlegener Technik aus der Zeit vorm Mauerfall
						laufen auch die anspruchsvollsten Spiele ohne Ruckler.
					</p>
				</div>
				<div slot="image">
					<img src="assets/hightech_pc.jpg" alt="Hightech PC bild"/>
				</div>
			</ContentWindow>
			<ContentWindow>
				<div slot="text" class="content-window-text">
					<h3>Andachtsstätte</h3>
					<p>
						Dank göttlichen Beistands werden hier nur Siegreiche
						Fußballspiele gezeigt
					</p>
				</div>
				<div slot="image">
					<img src="assets/jesus.jpg" alt="Göttlicher Beistand"/>
				</div>
			</ContentWindow>
			<ContentWindow>
				<div slot="text" class="content-window-text">
					<h3>Urlaubsfeeling</h3>
					<p>
						Eintauchen in den tropisch-fruchtig-frischen Flair des
						Lokalen Gollers dank speziell importierter Südseepalmen
					</p>
				</div>
				<div slot="image">
					<img src="assets/dschungel.jpg" alt="Dschungel"/>
				</div>
			</ContentWindow>
		</ColumnContainer>

		<About></About>
	</div>
</main>

<style>

	.content-window-text {
		padding: 10px;
	}

	.content-grid {
		display: grid;
		justify-content: center;
		justify-items: center;
		grid-template-columns: 25% minmax(250px, 25%) minmax(250px, 25%) 25%;
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
