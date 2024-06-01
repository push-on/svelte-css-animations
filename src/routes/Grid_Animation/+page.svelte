<script>
  import { onMount } from "svelte"
  import { animate } from "motion"

  const rows = 15
  const cols = 15

  const calculateStagger = (index) => {
    const row = Math.floor(index / cols)
    const col = index % cols
    const centerRow = (rows - 1) / 2
    const centerCol = (cols - 1) / 2
    const distanceFromCenter = Math.sqrt(
      (row - centerRow) ** 2 + (col - centerCol) ** 2
    )
    return distanceFromCenter * 0.1
  }

  onMount(() => {
    const boxes = document.querySelectorAll(".box")
    const staggerValues = Array.from({ length: rows * cols }, (_, i) =>
      calculateStagger(i)
    )
    boxes.forEach((box, index) => {
      animate(
        box,
        {
          opacity: [0, 1],
          scale: [1, 1.2, 0],
          rotate: [0, 180],
        },
        {
          duration: 1.5,
          delay: staggerValues[index],
          easing: "cubic-bezier(.22,.2,0,.99)",
          repeat: Infinity,
        }
      )
    })
  })
</script>

<main>
  <div class="grid">
    {#each Array(rows * cols) as _, i}
      <div class="box"></div>
    {/each}
  </div>
</main>

<style lang="scss">
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
  }
  .grid {
    display: grid;
    grid-template-columns: repeat(15, 1fr);
    gap: 10px;
    width: 800px;

    aspect-ratio: 1 / 1;
    overflow: hidden;
    @media (max-width: 900px) {
      width: 450px;
      height: 450px;
    }
  }

  .box {
    width: 30px;
    height: 30px;
    border-radius: 0.375rem;
    background-color: #786feb;
    will-change: transform, opacity;
    @media (max-width: 900px) {
      width: 20px;
      height: 20px;
    }
  }
</style>
