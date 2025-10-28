<script lang="ts">
	import AnimatedBg from "./AnimatedBg.svelte";
	import SocialMeta from "$lib/components/SocialMeta.svelte";
</script>

<!-- <svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head> -->

<SocialMeta />

<section>
	<div class="title-container">
		<img src="/cinema_buns_logo.png" alt="Logo" />
		<h1>
			<span id="cops">Cinema</span>
			<!-- <span id="vs">Vs</span> -->
			<span id="ninjas">Buns</span>
		</h1>
	</div>
	<div>
		<h2>A podcast about movies that's worth your time.</h2>
	</div>
</section>

<section>
	<div class="host-section">
		<h2>Hosted by...</h2>
		<div class="hosts-container">
			<div class="host-blurb">
				<h2 class="scott-font">Scott Wood</h2>
				<img src="/scott.png" alt="Scott Wood Profile" />
				<p>
					Scott is a natural storyteller who knows quality when he
					sees it. You can count on him to share the stories behind
					the people who made it happen.
				</p>
			</div>
			<div class="host-blurb">
				<h2 class="butler-font">Butler Fuqua</h2>
				<img src="/butler.png" alt="Butler Fuqua Profile" />
				<p>
					Butler is a self-proclaimed structure nerd with a passion
					for great dialogue. Expect an insight you didn't see coming
					that makes you rethink how a scene really works.
				</p>
			</div>
		</div>
	</div>
</section>

<AnimatedBg />

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		min-height: 100%;
		/* background-color: blue; */
		margin: auto;
		max-width: var(--site-width);
	}

	section div {
		padding: var(--default-padding);
		/* background-color: rgba(0, 0, 0, 0.9); */
	}

	h1 {
		margin: 0;
		font-family: var(--font-display);
		font-weight: 600;
		font-style: normal;
		font-size: clamp(1rem, 20dvw, 9rem);
	}

	h1 span {
		display: block;
		white-space: nowrap;
	}

	h1 span#cops {
		color: var(--yellow-color);
	}
	h1 span#vs {
		color: var(--red-color);
	}
	h1 span#ninjas {
		color: var(--orange-color);
	}

	h2 {
		margin: 0;
	}

	.title-container {
		position: relative;
		display: flex;
		justify-content: space-between;
		flex-direction: column;
		align-items: center;
	}
	/* .title-container h1 {
		z-index: 10;
		position: absolute;
	}
		*/
	.title-container img {
		width: 300px;
		max-width: 100%;
		border-radius: 5px;
		border: 2px solid #fefefe;
	}

	.host-container {
		display: flex;
	}

	.host-blurb img {
		width: 400px;
		max-width: 100%;
		border-radius: 5px;
	}
</style>
