<script>
	import { onMount } from 'svelte';

	let gigs = [];

	onMount(async () => {
		gigs = [
			{ date: 'March 10, 2025', venue: 'The Facebar, Reading', link: '#' },
			{ date: 'March 24, 2025', venue: 'Purple Turtle, London', link: '#' }
		];
	});
</script>

<main>
	<section class="hero">
		<h1>Welcome to SHINHAWK</h1>
		<p>The only band dedicated to the power of shins and hawks! #weLoveFeet</p>
	</section>

	<section class="gigs">
		<h2>Upcoming Gigs</h2>
		<ul class="gig-list">
			{#each gigs as gig}
				<li>
					<strong>{gig.date}</strong> - {gig.venue} <a href={gig.link}>[Tickets]</a>
				</li>
			{/each}
		</ul>
	</section>

	<section class="meet-the-band">
		<h2>Meet the Band</h2>
		<img src="/Meet-the-band.png" alt="Skinhawk Band Photo" />
		<div class="band-members">
			<div class="band-member"><strong>Guitarist:</strong> IDK some emo vampire gal</div>
			<div class="band-member"><strong>Drummer:</strong> Mustache Man</div>
			<div class="band-member"><strong>Vocalist:</strong> Scary dude</div>
			<div class="band-member"><strong>Bassist:</strong> Jezza</div>
		</div>
	</section>
	<section class="socials">
		<h2>Follow Us</h2>
		<a href="#">Facebook</a>
		<a href="#">Instagram</a>
		<a href="#">YouTube</a>
		<a href="#">Bandcamp</a>
	</section>

	<footer class="footer">
		&copy; 2025 SHINHAWK - All Rights Reserved. Stay Loud, Stay Shin-tastic!
	</footer>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Bangers&display=swap');

	:global(body) {
		background: #000;
		color: #fff;
		font-family: 'Bangers', sans-serif;
		margin: 0;
		overflow-x: hidden;
	}
	.hero {
		text-align: center;
		padding: 6rem 2rem;
		background: url('/SHINHAWK.jpg') no-repeat center;
		background-size: cover;
		position: relative;
		animation: flicker 1.5s infinite alternate;
		border-bottom: 5px solid #ffcc00;
	}
	.hero h1 {
		font-size: 5rem;
		color: #caf0f8;
		text-shadow:
			6px 6px 0 #0077b6,
			-6px -6px 0 #ffcc00;
		animation: shake 0.5s infinite alternate;
	}
	.hero p {
		font-size: 1.8rem;
		text-shadow: 3px 3px 0 #ffcc00;
		animation: pulse 1s infinite alternate;
	}
	.gigs {
		text-align: center;
		padding: 3rem;
		background: #222;
		border-top: 4px solid #ffcc00;
	}
	.gigs h2 {
		color: #00b4d8;
		font-size: 2.8rem;
		text-shadow: 3px 3px 0 #ffcc00;
	}
	.gig-list {
		list-style: none;
		padding: 0;
	}
	.gig-list li {
		background: #333;
		margin: 15px 0;
		padding: 15px;
		border-left: 8px solid #ffcc00;
		transition:
			transform 0.2s,
			background 0.3s;
	}
	.meet-the-band {
		text-align: center;
		padding: 4rem;
		background: #111;
		border-top: 4px solid #ffcc00;
	}
	.meet-the-band img {
		max-width: 80%;
		border: 5px solid #ffcc00;
		border-radius: 10px;
		margin-bottom: 2rem;
		display: block;
		margin-left: auto;
		margin-right: auto;
	}

	.band-members {
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 1.5rem;
	}

	@media (max-width: 768px) {
		.band-members {
			grid-template-columns: repeat(2, 1fr);
		}
	}

	@media (max-width: 480px) {
		.band-members {
			grid-template-columns: 1fr;
		}
	}
	.band-member {
		background: #222;
		padding: 1.5rem;
		border-radius: 8px;
		text-shadow: 2px 2px 0 #ffcc00;
		transition: transform 0.2s;
	}
	.socials {
		text-align: center;
		padding: 2rem;
		background: #000;
		border-top: 4px solid #00ff00;
	}
	.socials a {
		color: #00ff00;
		font-size: 1.8rem;
		margin: 0 15px;
		text-decoration: none;
		transition:
			color 0.3s,
			transform 0.2s;
	}
	.footer {
		text-align: center;
		padding: 1.5rem;
		background: #111;
		font-size: 1rem;
		border-top: 2px solid #ffcc00;
	}
</style>
