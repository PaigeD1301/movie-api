<script>
  import MovieDetails from './MovieDetails.svelte';

  export let movie;
  let showDetails = false;

  const movieDetails = () => {
    showDetails = !showDetails;
  };
</script>

<div class="movie-card">
  <img
    src={'https://image.tmdb.org/t/p/w500' + movie.poster_path}
    alt={movie.title}
    on:click={movieDetails}
  />
  <div class="description">
    <h2>{movie.title}</h2>
    <p>{movie.release_date}</p>
  </div>
</div>

{#if showDetails}
  <div>
    <MovieDetails {movie} on:hide={movieDetails} />
  </div>
{/if}

<style>
  img {
    width: 100%;
    height: auto;
    object-fit: cover;
    border-radius: 1rem;
    margin-bottom: 1rem;
    transition: linear 0.2s;
  }
  img:hover {
    scale: 1.1;
  }
  .movie-card {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    padding: 0.5rem;
  }
  .description {
    height: 5vh;
    padding: 1rem 0;
  }
  h2 {
    font-size: 1.1rem;
    margin-bottom: 0.5rem;
  }
  p {
    font-size: 0.9rem;
    color: #c7c7c7;
  }
</style>
