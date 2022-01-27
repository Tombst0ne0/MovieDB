<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/search/movie?api_key=adf5c3c3a673d2536838b47e929c6282&language=en-US&query=${params.id}&page=1&include_adult=false`
		);
		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { searchedMovie: data.results }
			};
		}
	}
</script>

<script>
	import MovieCard from 'MovieDB/moviedb/src/components/MovieCard.svelte';
	export let searchedMovie;
</script>

<div class="searched-movies">
	{#each searchedMovie as movie}
		<MovieCard {movie} />
	{/each}
</div>

<style>
	.searched-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 1rem;
		grid-row-gap: 2rem;
		height: 20vh;
	}
</style>
