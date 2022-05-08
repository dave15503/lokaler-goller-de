<script>
	import Headbar from "./Headbar.svelte";
</script>

<main>
	<Headbar></Headbar>
	<span class="main-content">
		Content will go here
	</span>

</main>

<style>



	main {
		width: 100vw;
		height: 100vh;

		display: grid;
		justify-content: center;
		justify-items: center;
		grid-template-columns: 20% minmax(1000px,60%) 20%;
		grid-template-rows: 100% auto;
	}

	.main-content {
		grid-column: 2/2;
		grid-row: 2/2;

		text-align: center;
	}	


</style>