<script>
  import { getContext } from "svelte"
  const { theme, toggle } = getContext("theme")
</script>

<style>
  .toggle {
    position: absolute;
    right: 20px;
    top: 20px;
    display: flex;
    align-items: center;
  }

  input[type="checkbox"] {
    height: 0;
    width: 0;
    visibility: hidden;
  }

  label {
    cursor: pointer;
    text-indent: -9999px;
    width: 60px;
    height: 28px;
    box-shadow: -7px -7px 15px var(--theme-shadowOne),
      7px 7px 15px var(--theme-shadowTwo),
      inset -7px -7px 15px var(--theme-shadowOne),
      inset 7px 7px 15px var(--theme-shadowTwo);
    background-color: var(--theme-background);
    transition: all 200ms linear;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: 100px;
    border: 5px solid var(--theme-background);
    position: relative;
  }

  label:after {
    content: "";
    background-color: var(--theme-background);
    box-shadow: inset 7px 7px 15px var(--theme-shadowOne),
      inset -7px -7px 15px var(--theme-shadowTwo);
    width: 22px;
    height: 22px;
    border-radius: 50%;
    position: absolute;
    left: 5px;
    transition: ease-in-out 200ms;
  }

  input:checked + label {
    background-color: var(--theme-background);
    transition: all 200ms linear;
  }

  input:checked + label:after {
    left: calc(100% - 5px);
    transform: translateX(-100%);
  }
</style>

<div class="toggle">
  <input
    class="toggle-switch"
    type="checkbox"
    id="toggle-switch"
    name="mode"
    on:click={toggle} />
  <label for="toggle-switch">
    <span class="screen-reader-text">Toggle Color Scheme</span>
  </label>
</div>
