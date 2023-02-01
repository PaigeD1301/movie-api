<script context="module">
  export let details;

  export async function load({ fetch, params }) {
    const res = await fetch(
      `https://api.themoviedb.org/3/movie/${params.id}?api_key=98ce9354af181e62179e2e1b708c0451&language=en-US&page=1`
    );
    const details = await res.json();
    if (res.ok) {
      return {
        props: { details },
      };
    }
  }
</script>

<div class="movie-details">
  <div class="img-container">
    <img
      src={'https://image/tmdb.org/t/p/original' + details.backdrop_path}
      alt={details.title}
    />
  </div>
  <div class="txt-container">
    <h1>{details.title}</h1>
    <p class="overview">{details.overview}</p>
    <p><span>Release Date</span>{details.release_date} <br /></p>
  </div>
</div>
