<script>
	import Headbar from "./Headbar.svelte";
	import Bar from "./Bar.svelte";
	import Host from "./Host.svelte";
	import About from "./About.svelte";
</script>

<main>
	<Headbar></Headbar>
	
	<Bar></Bar>
	<Host></Host>
	<About></About>

</main>

<style>



	main {
		width: 100vw;
		height: 100vh;

		display: grid;
		justify-content: center;
		justify-items: center;
		grid-template-columns: 20% minmax(500px,30%) minmax(500px, 30%) 20%;
		grid-template-rows: 100% repeat(auto, 5);
	}

	main::after{
		height: 2000px;
	}

</style>