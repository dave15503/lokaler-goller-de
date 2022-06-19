<script>
	import router from "page"
	import Home from "./routes/Home.svelte"
	import Fbs from "./routes/Fbs.svelte"

	let page
	router("/",() => page = Home)
	router("/fbs", () => page = Fbs)
	router.start()

</script>

<svelte:component this={page}></svelte:component>