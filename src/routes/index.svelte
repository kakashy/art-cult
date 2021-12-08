<script>
	import { fly, fade } from 'svelte/transition';
</script>

<svelte:head>
	<title>Art Culture</title>
</svelte:head>
<header>
	<a href="/"> Art Cult </a>
</header>

<section>
	<div class="intro">
		<p class="summer" in:fly={{ duration: 700, x: -20 }}>THIS SUMMER</p>
		<h1 in:fade={{ duration: 800 }}>Music & Perfomance Art Festival</h1>
		<p class="duration" in:fly={{ duration: 700, x: -20 }}>15 - 19 June 2021</p>
		<div class="ticketing" in:fly={{ duration: 700, y: 50 }}>
			<a href="/ticket">
				<button>Buy Ticket</button>
			</a>
			<a href="/ac">Learn more about the event</a>
		</div>
	</div>
	<div class="promo" />
</section>

<footer>
	<a href="/social">instagram</a>
	<a href="/social">twitter</a>
	<a href="/social">eventz</a>
</footer>

<style>
	header {
		text-transform: uppercase;
		position: absolute;
		top: 20px;
		left: 20px;
		font-family: abba;
		font-size: 2rem;
	}
	section {
		display: flex;
		flex-direction: column;
		justify-items: center;
	}
	.intro {
		display: flex;
		flex-direction: column;
		align-items: flex-start;
		justify-items: center;
		margin: auto 0;
		padding: 0 10px;
	}
	.summer {
		font-size: 0.8rem;
		font-weight: bold;
		opacity: 0.5;
	}
	.duration {
		font-size: 1.2rem;
		opacity: 0.7;
	}
	h1 {
		font-size: 4rem;
		font-weight: 500;
		margin: 1rem 0;
		font-family: new-normal;
		transition: text-shadow 0.2s ease-in-out;
	}
	h1:hover {
		/* color: #ffd000; */
		text-shadow: 1px 1px 10px #ffd000;
	}
	a button {
		font-weight: bold;
		border-radius: 2px;
	}
	.promo {
		background-image: url('/media/mp.jpg');
		background-size: cover;
	}
	.ticketing {
		width: 100%;
		display: flex;
		align-items: center;
		gap: 2rem;
	}
	footer {
		text-transform: uppercase;
		font-size: 0.8rem;
		font-weight: bold;
	}
	@media screen and (min-width: 550px) {
		section {
			height: 90vh;
		}
		.promo {
			background-image: linear-gradient(to right, black, #000000aa, transparent),
				url('/media/mp.jpg');
			background-position: left;
			position: fixed;
			width: 100vw;
			height: 100vh;
			top: 0;
			left: 0;
			z-index: -1;
		}
		.intro {
			width: 45%;
		}
		footer {
			position: fixed;
			right: -5pc;
			top: 50%;
			z-index: 2;
			display: flex;
			flex-direction: row;
			align-items: center;
			transform: rotate(270deg);
			margin: auto;
			background-color: rgba(0, 0, 0, 0.637);
		}
		footer a {
			margin: 0 10px;
		}
	}
	@media screen and (max-width: 550px) {
		section {
			flex-direction: column-reverse;
		}
		.intro {
			align-items: center;
		}
		h1 {
			font-size: 3rem;
			text-align: center;
		}
		.ticketing {
			justify-content: space-evenly;
		}
		.promo {
			position: relative;
			width: 100vw;
			height: 300px;
			background-position: bottom;
		}
		footer {
			display: flex;
			flex-direction: row;
			align-items: center;
			justify-content: space-evenly;
			margin: 5rem 0;
		}
	}
</style>
