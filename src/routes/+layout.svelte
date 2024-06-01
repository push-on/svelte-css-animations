<script>
  import "../style.css"
  import { fly } from "svelte/transition"
  import { cubicIn, cubicOut } from "svelte/easing"
  import HomeLink from "../components/HomeLink.svelte"
  import OG_img from "../assets/anim.webp"
  export let data

  const duration = 300
  const delay = duration + 100
  const y = 10

  const transitionIn = { easing: cubicOut, y, duration, delay }
  const transitionOut = { easing: cubicIn, y: -y, duration }
</script>

<svelte:head>
  <title>Animations</title>
  <meta name="description" content={"web animations"} />
  <meta name="og:title" content={"Web Animations"} />
  <meta name="og:image" content={OG_img} />
  <meta name="twitter:card" content="summary_large_image" />
</svelte:head>
{#key data.pathname}
  <div in:fly={transitionIn} out:fly={transitionOut}>
    {#if data.pathname !== "/"}
      <HomeLink />
    {/if}
    <slot />
  </div>
{/key}
