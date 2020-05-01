<script>
  import ThemeToggle from "./Theme/ThemeToggle.svelte"
  import ThemeContext from "./Theme/ThemeContext.svelte"
  import Button from "./Button.svelte"
  import LinkedInIcon from "./Icons/LinkedIn.svelte"
  import GithubIcon from "./Icons/Github.svelte"
  import TwitterIcon from "./Icons/Twitter.svelte"
  import Hero from "./Hero.svelte"
</script>

<style>
  :global(html) {
    background-color: var(--theme-background);
    color: var(--theme-text);
    transition: background-color 200ms linear;
  }

  :global(body) {
    font-family: "Dosis", sans-serif;
  }

  main {
    display: flex;
    justify-content: center;
    height: 100%;
    align-items: center;
  }

  .buttonsWrapper {
    position: absolute;
    bottom: 20px;
    left: 20px;
    display: flex;
  }
  :global(svg[ref="social"]) {
    color: var(--theme-text);
    width: 22px;
    height: 22px;
    transition: color 0.1s linear;
  }
</style>

<svelte:head>
  <title>Homepage | Dmitri Karasjov</title>
</svelte:head>
<ThemeContext>
  <main>
    <ThemeToggle />
    <Hero />
    <div class="buttonsWrapper">
      <Button link="https://www.linkedin.com/in/dmitrikarasjov/">
        <LinkedInIcon />
      </Button>
      <Button link="https://github.com/dimo89">
        <GithubIcon />
      </Button>
      <Button link="https://twitter.com/DmitriKarasjov">
        <TwitterIcon />
      </Button>
    </div>
  </main>
</ThemeContext>
