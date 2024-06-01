<script>
  import { animate } from "motion"
  import { onMount } from "svelte"

  const x = "0%"
  const y = "33%"
  onMount(() => {
    animate(
      ".position_one",
      {
        top: [x, y, y, x, x],
        left: [y, y, x, x, y],
      },
      { easing: "linear", repeat: Infinity, duration: 3 }
    )
    animate(
      ".position_two",
      {
        top: [x, y, y, x, x],
        left: [y, y, x, x, y],
      },
      { easing: "linear", repeat: Infinity, delay: 1.5, duration: 3 }
    )
  })
</script>

<div class="ball position_one"></div>
<div class="ball position_two"></div>

<style lang="scss">
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
  .position_two {
    transform: translateX(500px) translateY(200px);
  }
  .position_one {
    transform: translateX(500px) translateY(200px);
  }
</style>
