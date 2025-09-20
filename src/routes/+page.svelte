<script lang="ts">
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
	<h1>
		<span id="cops">Cops</span>
		<span id="vs">Vs</span>
		<span id="ninjas">Ninjas</span>
	</h1>
	<div>
		<h2>
			A podcast that interviews real-life heroes such as police officers,
			church pastors, mentors, veterans, therapists, nurses, and more.
		</h2>
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		min-height: 100%;
		background-color: blue;
		margin: auto;
		max-width: var(--site-width);
	}

	section div {
		padding: var(--default-padding);
	}

	h1 {
		margin: 0;
		font-family: "Bungee Shade", sans-serif;
		font-weight: 600;
		font-style: normal;
		font-size: clamp(1rem, 20dvw, 9rem);
	}

	h1 span {
		display: block;
		white-space: nowrap;
	}

	h2 {
		margin: 0;
	}
</style>
