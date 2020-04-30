<script>
  import ThemeToggle from "./ThemeToggle.svelte"
  import ThemeContext from "./ThemeContext.svelte"
</script>

<style>
  :global(html) {
    background-color: var(--theme-background);
    color: var(--theme-text);
    transition: background-color 200ms linear;
  }

  main {
    text-align: center;
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<svelte:head>
  <title>DK</title>
</svelte:head>
<ThemeContext>
  <main>
    <ThemeToggle />
  </main>
</ThemeContext>
