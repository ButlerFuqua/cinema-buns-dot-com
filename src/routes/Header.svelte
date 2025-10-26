<script lang="ts">
	import { page } from "$app/state";
	import logo from "$lib/images/svelte-logo.svg";
	import github from "$lib/images/github.svg";
</script>

<header>
	<a href="#">Connect</a>
	<a href="#">Ask a question</a>
</header>

<style>
	header {
		height: 100%;
		padding: var(--default-padding);
		max-width: var(--site-width);
		margin: auto;
		display: flex;
		justify-content: space-between;
		align-items: center;
		background: var(--default-bg);
	}
	header * {
		margin: 0;
	}

	header a {
		background-color: var(--default-bg);
		text-decoration: none;
		/* font-family: var(--font-display); */
		font-family: "Rampart One", sans-serif;
		font-weight: 00;
		font-style: normal;
		font-size: 1.3rem;
		color: var(--yellow-color);
		/* font-family: "Nabla", system-ui;
		font-optical-sizing: auto;
		font-weight: 400;
		font-style: normal;
		font-variation-settings:
		"EDPT" 100,
		"EHLT" 12; */
	}
	
	header a + a {
		color: #fefefe;
		background-color: var(--default-bg);
		text-align: right;
	}
</style>
