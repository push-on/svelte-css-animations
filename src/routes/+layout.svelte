<script>
  import "../style.css"
  import { fly } from "svelte/transition"
  import { cubicIn, cubicOut } from "svelte/easing"
  import HomeLink from "../components/HomeLink.svelte"
  export let data

  const duration = 300
  const delay = duration + 100
  const y = 10

  const transitionIn = { easing: cubicOut, y, duration, delay }
  const transitionOut = { easing: cubicIn, y: -y, duration }
</script>

{#key data.pathname}
  <div in:fly={transitionIn} out:fly={transitionOut}>
    {#if data.pathname !== "/"}
      <HomeLink />
    {/if}
    <slot />
  </div>
{/key}
