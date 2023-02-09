<script>
  let input = '';
  let active = false;
</script>

<form class="seach">
  <!-- {#if !active}
    <label for="seach_movie">Enter keyword</label> -->
  <!-- {/if} -->
  <input
    type="text"
    on:focus={() => (active = true)}
    bind:value={input}
    name="search_movie"
    placeholder="enter keyword"
  />
  <button>Search</button>
</form>

<style>
  form {
    float: right;
  }
</style>
