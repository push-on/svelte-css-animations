<script>
  import { onMount } from "svelte"
  import { animate} from "motion"

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
          delay: calculateStagger(index),
          easing: "cubic-bezier(.22,.2,0,.99)",
          repeat: Infinity,
        }
      )
    })
  })
</script>

<div class="grid">
  {#each Array(rows * cols) as _, i}
    <div class="box"></div>
  {/each}
</div>

<style lang="scss">
  .grid {
    display: grid;
    grid-template-columns: repeat(15, 1fr);
    gap: 10px;
  }

  .box {
    width: 50px;
    height: 50px;
    border-radius: 0.375rem;
    background-color: #786feb;
  }
</style>
