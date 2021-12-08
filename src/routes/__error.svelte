<script context="module">
	/**
	 * @returns {object}
	 * @param status
	 */
	export function load({ status }) {
		return {
			props: { status }
		};
	}
</script>

<script>
	export let status;
</script>

<svelte:head>
	<title>{status} / Art Culture</title>
</svelte:head>
<section>
	<div class="stat">Error {status}</div>

	<div>
		{#if status === 404}
			<p>This page doesn't exist. Sorry.</p>
		{:else if status === 500}
			<p>😪This one is on us. Try reloading this page or try another time.</p>
		{:else}
			<p>😬This shouldn't happen. <a sveltekit:prefetch href="/">Go back home?</a></p>
		{/if}
	</div>
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		height: 100vh;
	}
	.stat {
		background-color: black;
		color: #ffd000;
		font-size: 2rem;
		padding: 8px;
		border-radius: 3px;
		box-shadow: 1px 1px 8px #00000050;
	}
</style>
