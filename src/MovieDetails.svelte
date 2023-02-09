<script>
  import { createEventDispatcher } from 'svelte';
  export let movie;
  //   export let hideDetails;

  const dispatch = createEventDispatcher();

  function hideDetails() {
    dispatch('hide', {
      text: 'Pass to MovieCard component',
    });
  }
</script>

<main on:click={hideDetails}>
  <section class="overlay">
    <div class="movie-details">
      <div class="img-container">
        <img
          src={'https://image.tmdb.org/t/p/original' + movie.poster_path}
          alt={movie.title}
        />
      </div>
      <div class="txt-container">
        <h1>{movie.title}</h1>
        <p class="overview">{movie.overview}</p>
        <p>
          <span>Release Date: </span>{movie.release_date}
        </p>
        <p>
          <span>Rating: </span>{movie.vote_average} <br />
        </p>
      </div>
    </div>
  </section>
</main>

<style>
  .overlay {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, 0.7);
    opacity: 1;
    transform: scale(1.1);
    transition: linear 0.24s;
  }
  .movie-details {
    width: 27rem;
    max-width: 70vw;
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    background-color: rgba(0, 0, 0, 0.5);
    padding: 1.5rem;
    border-radius: 0.5rem;
  }
  .img-container {
    width: 100%;
    border-radius: 2rem;
  }
  img {
    width: 100%;
  }
  h1 {
    padding: 0.5rem 0rem;
    font-size: 1.1rem;
  }
  p {
    font-size: 0.8rem;
    padding: 3px;
  }
  span {
    font-weight: bold;
  }
</style>
