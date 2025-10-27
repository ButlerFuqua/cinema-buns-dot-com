<script lang="ts">
	import { page } from "$app/state";
	import logo from "$lib/images/svelte-logo.svg";
	import github from "$lib/images/github.svg";
    import Modal from "./Modal.svelte";
    import SocialLinks from "./SocialLinks.svelte";

	let showHostsModal = false;
	let showConnectModal = false;
</script>

<header>
	<a href="#" on:click={() => showConnectModal = true}>Connect</a>
	<a href="#" on:click={() => showHostsModal = true}>Hosts</a>
	<a href="#" >Ask a question</a>

	<Modal isOpen={showHostsModal} onClose={() => (showHostsModal = false)}>
        <div class="modal-content">
            <h2>Hosted by...</h2>
            <div class="hosts-container">
                <div class="host-blurb">
					<img src="/cops_vs_ninjas_logo.png" alt="Scott Wood Profile" />
					<h2>Scott Wood</h2>
					<p>Scott Wood is a person. he is the host of the show. That is who is is, and that is what he does, relative to this podcast and website.</p>
				</div>
                <div class="host-blurb">
					<img src="/cops_vs_ninjas_logo.png" alt="Scott Wood Profile" />
					<h2>Scott Wood</h2>
					<p>Scott Wood is a person. he is the host of the show. That is who is is, and that is what he does, relative to this podcast and website.</p>
				</div>
            </div>
        </div>
    </Modal>
	<Modal isOpen={showConnectModal} onClose={() => (showConnectModal = false)}>
		<br />

		<div style="display: flex; justify-content:center; align-items:center; flex-direction:column">
			<h2>Join our mailing list!</h2>
		<p>We won't share your email or annoy you.</p>
		</div>

		<div style="display: flex; justify-content:center; align-items:center; flex-direction:column">

			<!-- EMAIL SUBSCRIBE FORM HERE -->
		 <script async src="https://subscribe-forms.beehiiv.com/embed.js"></script><iframe src="https://subscribe-forms.beehiiv.com/ae428906-d088-4220-8bb8-8d7490e11b2d" class="beehiiv-embed" data-test-id="beehiiv-embed" frameborder="0" scrolling="no" style="width: 560px; height: 206px; margin: 0; border-radius: 0px 0px 0px 0px !important; background-color: transparent; box-shadow: 0 0 #0000; max-width: 100%;"></iframe>
	<!-- EMAIL SUBSCRIBE FORM HERE -->

		</div>
        <div class="modal-content">
            <h2 style="text-align: center;">Follow Cinema Buns on...</h2>
			<br />
            <SocialLinks />
        </div>
    </Modal>
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

	.hosts-container{
		display: flex;
		flex-direction: column;
	}
	.host-blurb {
		display: flex;
		flex-direction: column;
		margin: 1rem auto;
	}
	.host-blurb img {
		max-width: 100%;
		border-radius: 5px;
	}
</style>
