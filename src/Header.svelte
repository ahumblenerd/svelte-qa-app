<script>
    export let links = [];
</script>

<header class="navbar">
  <section class="navbar-section">
  {#each links as link }
    <a href="{link.url}" class="navbar-brand mr-2">{link.name}</a>
    {/each}
  </section>
</header>