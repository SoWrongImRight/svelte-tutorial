<script>
  export let repositories;

  let userSearchTerm = "";

  $: filteredRepos = repositories.filter((repo) => {
    return repo.name.toLowerCase().includes(userSearchTerm.toLocaleLowerCase())
  })
</script>

<style>
    ul {
      list-style: none;
      margin: 0;
      padding: 0;
    }
    li {
      padding: 10px 5px;
    }
    li:nth-child(odd) {
      background-color: lightblue;
    }
    code {
      display: block;
    }
    .search-wrapper {
      border: 1px solid #ccc;
      border-radius: 10px;
      padding: 5px;
      marging: 10px auto;
    }
    .search-form input {
      border-top-left-radius: 10px;
      border-top-right-radius: 10px;
      width: 100%;
    }
</style>

<div class="search-wrapper">
  <form class="search-form">
    <input type="text" bind:value={userSearchTerm} placeholder="Search for repositories" />
  </form>
  <ul>
    {#each filteredRepos as repository}
      <li><strong>{repository.name}</strong> <code>{repository.url}</code></li>
    {/each}
  </ul>
</div>
