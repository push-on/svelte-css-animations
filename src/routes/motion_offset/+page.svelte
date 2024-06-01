<script>
  import { animate } from "motion"
  import { onMount } from "svelte"

  const x = "0%"
  const y = "80%"
  onMount(() => {
    animate(
      ".position_one",
      {
        top: [x, y, y, x, x],
        left: [y, y, x, x, y],
      },
      { easing: "linear", repeat: Infinity, duration: 2 }
    )
    animate(
      ".position_two",
      {
        top: [x, y, y, x, x],
        left: [y, y, x, x, y],
      },
      { easing: "linear", repeat: Infinity, delay: 1, duration: 2 }
    )
  })
</script>

<main>
  <div class="ball position_one"></div>
  <div class="ball position_two"></div>
</main>

<style lang="scss">
  main {
    overflow: hidden;
    border: 1px solid white;
    width: 100vw;
    height: 100vh;

  }
  .ball {
    width: 100px;
    height: 100px;
    border-radius: 9999px;
    background: radial-gradient(
      circle at 30% 30%,
      #fff9da,
      #fee140,
      #fa709a,
      #50051b
    );

    position: absolute;
  }

  
</style>
