<script>
  //   import { Router, Route } from 'svelte-routing';
  import { onMount } from 'svelte';
  import Movies from './Movies.svelte';

  export let movies;

  onMount(async function () {
    const response = await fetch(
      'https://api.themoviedb.org/3/movie/popular?api_key=98ce9354af181e62179e2e1b708c0451&language=en-US&page=1'
    );
    const data = await response.json();
    console.log(data);

    movies = data.results;
  });
</script>

<section class="main">
  <h1>MOVIE DATABASE</h1>
  {#if movies}
    <Movies {movies} />
  {/if}
</section>

<style>
</style>
