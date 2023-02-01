<script>
  //   import { Router, Route } from 'svelte-routing';
  import { onMount } from 'svelte';
  import Movies from './Movies.svelte';

  export let movies;

  const fetchMovies = async () => {
    const response = await fetch(
      'https://api.themoviedb.org/3/movie/popular?api_key=98ce9354af181e62179e2e1b708c0451&language=en-US&page=1'
    );
    const data = await response.json();
    console.log(data);

    movies = data.results;
  };

  onMount(fetchMovies);
</script>

{#if movies}
  <Movies {movies} />
{/if}
