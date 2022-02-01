<script>
	export let popular;
	import MovieCard from './MovieCard.svelte';
</script>

<h3>Popular Movies</h3>
<h4>(Source TMDB.org)</h4>
<div class="popular-movies">
	{#each popular as movie}
		<MovieCard {movie} />
	{/each}
</div>

<style>
	h3 {
		padding: 0 1rem;
		font-size: 1.9rem;
	}
	h4 {
		padding: 0 1rem;
	}
	.popular-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 0rem;
		grid-row-gap: 2rem;
	}
</style>
