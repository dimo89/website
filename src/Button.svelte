<script>
  export let link
</script>

<style>
  button {
    background: none;
    border: none;
    outline: none;
    cursor: pointer;
    text-align: center;
    font-size: 1rem;
    margin-top: 1.5rem;
    color: black;
    width: 50px;
    height: 50px;
    line-height: 50px;
    letter-spacing: 0.5px;
    box-shadow: -9px -9px 18px var(--theme-shadowOne),
      9px 9px 18px var(--theme-shadowTwo);
    border-radius: 25px;
    margin-right: 20px;
  }

  button:hover :global(svg[ref="social"]) {
    color: #00e15e;
  }
</style>

<a href={link} target="_blank">
  <button>
    <slot />
  </button>
</a>
