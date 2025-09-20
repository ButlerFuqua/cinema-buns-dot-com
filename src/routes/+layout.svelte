<script lang="ts">
	import Header from "./Header.svelte";
	import "../app.css";
	import PodcastLinks from "./PodcastLinks.svelte";

	let { children } = $props();
</script>

<div class="app">
	<div class="header">
		<Header />
	</div>

	<main>
		{@render children()}
	</main>

	<footer>
		<div>
			<PodcastLinks />
		</div>
	</footer>
</div>

<style>
	.app {
		/* background: blue; */
		height: 100vh;
		height: 100dvh;
		display: flex;
		flex-direction: column;
	}

	.header {
		min-height: 60px;
		flex: 1;
		/* background-color: coral; */
	}
	main {
		/* background-color: teal; */
		flex: 11;
		overflow: auto;
	}
	footer {
		flex: 1;
		min-height: 60px;
		background-color: var(--default-bg);
	}

	footer div {
		max-width: var(--site-width);
		margin: auto;
	}
</style>
