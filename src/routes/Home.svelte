<script>
	import Headbar from "../components/Headbar.svelte";
	import About from "../components/About.svelte";
	import ImageScroller from "../components/ImageScroller.svelte";
	import SectionContainer from "../components/SectionContainer.svelte";


    let menuItems = [
        { id: 0, title: "Das Lokal", link: "#bar" },
        { id: 1, title: "Gastgeber", link: "#host" },
        { id: 2, title: "Impressum", link: "#about" },
    ];

	let scroller0ImgList = [
		{ alt: "Image 0", content: "linear-gradient(red, violet)"},
		{ alt: "Image 1", content: "linear-gradient(blue, red)"},
		{ alt: "Image 2", content: "linear-gradient(green, yellow)"}
	];
</script>

<main>
	<Headbar {menuItems} />

	<div class="content-grid">
		<SectionContainer orientation="right" tag="bar" imagePath="" row="1">
			<h1>Das Lokal</h1>
			<p>
				Der Lokale Goller lädt regelmäßig zum entspannen in ruhiger und
				relaxter Atmosphäre ein.
			</p>
			<h2>Platzhaltertext</h2>
			<p>
				Lorem ipsum dolor sit amet, consectetur adipiscing elit. Cras
				sagittis quam condimentum, commodo neque vitae, mattis odio.
				Vestibulum sit amet commodo sapien. Mauris egestas vehicula
				luctus. Vivamus pulvinar vitae elit eu tempor. Proin congue sem
				feugiat mauris hendrerit dictum. Aenean lacus lorem, facilisis
				cursus quam quis, egestas ultrices mi. Sed dapibus magna ac leo
				pharetra, quis gravida magna tristique. Nunc ac tincidunt dolor,
				non sagittis nisi. Aenean condimentum, neque et hendrerit
				egestas, massa ligula aliquam nunc, fermentum ultricies nisi
				ante nec neque. Proin felis nisi, convallis quis ex eget,
				venenatis suscipit risus. Aenean pharetra orci eu turpis
				sagittis dignissim. Phasellus sapien lorem, dignissim vitae
				mollis eu, aliquet vitae augue. Duis fringilla elit nulla, a
				mattis lacus euismod vitae. Suspendisse potenti. Sed sapien
				orci, facilisis quis mauris vitae, pharetra rutrum quam. Nunc
				volutpat tincidunt cursus.
			</p>
			<p>
				Suspendisse eget dolor at lectus pellentesque dignissim. Ut
				placerat dolor ac elementum dictum. In eget nunc sit amet ipsum
				vestibulum ornare. In pulvinar turpis nec ante pharetra, in
				ornare lorem elementum. Phasellus lacinia velit vitae turpis
				condimentum, a aliquet neque finibus. Nunc nulla velit,
				facilisis eu laoreet pulvinar, rutrum eget turpis. Proin
				tincidunt, purus vel luctus molestie, mauris diam tristique leo,
				id cursus leo magna ac dolor. Curabitur et nibh ultricies leo
				eleifend blandit elementum sit amet risus.
			</p>
		</SectionContainer>

		<ImageScroller row="2" imagesList={scroller0ImgList}></ImageScroller>

		<SectionContainer orientation="left" tag="host" imagePath="" row="3">
			<h1>Ihre Gastgeber</h1>
			<h2>Gico Noller</h2>
			<p>
				Vestibulum in molestie sem. Vivamus quis finibus elit, eget
				venenatis mauris. Vestibulum laoreet neque ultricies pharetra
				tincidunt. Curabitur ac pretium nibh, sit amet vestibulum diam.
				Duis blandit leo a porttitor pharetra. Nulla porta rutrum
				blandit. Nam vel est eu ex blandit venenatis. Donec finibus
				turpis vitae bibendum sodales. Vestibulum erat sapien, aliquam
				nec lorem sodales, tristique dignissim risus. Donec fermentum
				molestie rhoncus. Sed facilisis purus a euismod ultricies. Sed
				suscipit dolor in tellus tristique, vel commodo leo convallis.
				Nunc luctus fringilla arcu id blandit. Nulla et mollis diam.
			</p>

			<h2>
				Prof. der Shishalogie und staatl. anerkanner Blubbermeister Elia
				"Zimt" Wundrich
			</h2>
			<p>
				Weiterer Platzhaltertext lalalalalalal wer das ließt ist doof...
			</p>
			<p>
				Maecenas at malesuada mauris. In hac habitasse platea dictumst.
				Sed at vehicula massa, sit amet luctus leo. Etiam sagittis
				cursus urna scelerisque accumsan. Pellentesque at rutrum tellus,
				ullamcorper efficitur libero. Morbi odio felis, semper sit amet
				porttitor quis, scelerisque sed velit. Donec in mauris mollis,
				aliquam orci ut, tincidunt quam. Curabitur ullamcorper, ex non
				tincidunt pellentesque, magna erat mollis ex, eget pulvinar urna
				mi vel purus. Sed ac porttitor justo. Phasellus vel sem tellus.
			</p>
		</SectionContainer>

		<About />
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
