<script>
	export let new;
	import MovieCard from './MovieCard.svelte';
</script>

<h3>New Movies</h3>
<div class="new-movies">
	{#each new as movie}
		<MovieCard {movie} />
	{/each}
</div>

<style>
	h3 {
		padding: 0 1rem;
		font-size: 1.9rem;
	}
	.new-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 0rem;
		grid-row-gap: 2rem;
	}
</style>
