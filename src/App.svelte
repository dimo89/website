<script>
  import ThemeToggle from "./Theme/ThemeToggle.svelte"
  import ThemeContext from "./Theme/ThemeContext.svelte"
  import Button from "./Button.svelte"
  import LinkedInIcon from "./Icons/LinkedIn.svelte"
  import GithubIcon from "./Icons/Github.svelte"
  import TwitterIcon from "./Icons/Twitter.svelte"
  import Hero from "./Hero.svelte"
</script>

<svelte:head>
  <script>
    !(function () {
      var analytics = (window.analytics = window.analytics || [])
      if (!analytics.initialize)
        if (analytics.invoked)
          window.console &&
            console.error &&
            console.error("Segment snippet included twice.")
        else {
          analytics.invoked = !0
          analytics.methods = [
            "trackSubmit",
            "trackClick",
            "trackLink",
            "trackForm",
            "pageview",
            "identify",
            "reset",
            "group",
            "track",
            "ready",
            "alias",
            "debug",
            "page",
            "once",
            "off",
            "on",
            "addSourceMiddleware",
            "addIntegrationMiddleware",
            "setAnonymousId",
            "addDestinationMiddleware",
          ]
          analytics.factory = function (e) {
            return function () {
              var t = Array.prototype.slice.call(arguments)
              t.unshift(e)
              analytics.push(t)
              return analytics
            }
          }
          for (var e = 0; e < analytics.methods.length; e++) {
            var key = analytics.methods[e]
            analytics[key] = analytics.factory(key)
          }
          analytics.load = function (key, e) {
            var t = document.createElement("script")
            t.type = "text/javascript"
            t.async = !0
            t.src =
              "https://cdn.segment.com/analytics.js/v1/" +
              key +
              "/analytics.min.js"
            var n = document.getElementsByTagName("script")[0]
            n.parentNode.insertBefore(t, n)
            analytics._loadOptions = e
          }
          analytics._writeKey = "ipSnRCJijEz2pTvRJ7aaVICPNMI3dXPo"
          analytics.SNIPPET_VERSION = "4.13.2"
          analytics.load("ipSnRCJijEz2pTvRJ7aaVICPNMI3dXPo")
          analytics.page()
        }
    })()
  </script>
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
