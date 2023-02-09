<script>
  import MovieCard from './MovieCard.svelte';
  export let movies;
</script>

<h2>Popular Movies</h2>
<div class="popular-movies">
  {#each movies as movie}
    <MovieCard {movie} />
  {/each}
</div>

<style>
  h2 {
    padding-left: 1.5rem;
  }
  .popular-movies {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    grid-column-gap: 1rem;
    grid-row-gap: 2rem;
    overflow: hidden;
    padding: 1rem;
  }
</style>
