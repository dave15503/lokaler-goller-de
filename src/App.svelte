<script>
	import Headbar from "./Headbar.svelte";
	import Bar from "./Bar.svelte";
	import Host from "./Host.svelte";
	import About from "./About.svelte";
</script>

<main>
	<Headbar />

	<div class="content-grid">
		<Bar />
		<Host />
		<About />
	</div>
</main>

<style>


	.content-grid {
		display: grid;
		justify-content: center;
		justify-items: center;
		grid-template-columns: 20% minmax(300px, 30%) minmax(300px, 30%) 20%;
		grid-template-rows: repeat(5, auto);
	}

	@media only screen and (max-width: 800px){

		.content-grid {
			grid-template-columns: 1fr;
			margin: 5px;
		}

	}
</style>
