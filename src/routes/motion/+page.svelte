<script>
  import { animate } from "motion"
  import { onMount } from "svelte"
  onMount(() => {
    animate(
      ".title",
      {
        scale: [1.2, 1.5],
        opacity: [0, 1],
        letterSpacing: ["0rem", ".6rem"],
      },
      {
        repeat: Infinity,
        duration: 1.5,
        easing: "cubic-bezier(.22,.2,0,.99)",
        direction: "alternate",
      }
    )
    animate(
      ".box",
      {
        rotate: [0, 350],
      },
      {
        repeat: Infinity,
        duration: 1.5,
        easing: "cubic-bezier(.22,.2,0,.99)",
        direction: "alternate",
      }
    )
    animate(
      ".ball",
      {
        y: [600, 0],
      },
      {
        repeat: Infinity,
        duration: 1.5,
        easing: "cubic-bezier(.22,.2,0,.99)",
        direction: "alternate",
      }
    )
  })
</script>

<h1 class="title">MOTION ONE</h1>
<div class="ball position-L"></div>
<div class="ball position-R"></div>
<div class="box"></div>
<div class="glass">GLASS</div>

<style lang="scss">
  .glass {
    text-align: center;
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 5rem;
    line-height: 1;
    position: absolute;
    color: rgba(0, 0, 0, 0.37);
    z-index: 1000;
    top: 2%;
    width: 50vw;
    height: 150px;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    box-shadow: 0 4px 40px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.47);
    left: 0;
    right: 0;
    margin: auto;
    @media (max-width: 640px) {
      width: 90vw;
      height: 100px;
      top: 5%;
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
    }
  }
  .ball {
    width: 200px;
    height: 200px;
    border-radius: 9999px;
    background: radial-gradient(
      circle at 30% 30%,
      #fff9da,
      #fee140,
      #fa709a,
      #50051b
    );

    position: absolute;
    transform: translateX(-50%);
    @media (max-width: 640px) {
      width: 100px;
      height: 100px;
    }
  }
  .box {
    width: 200px;
    height: 200px;
    border-radius: 20px;
    border: 1px solid rgba(255, 255, 255, 0.47);

    background-image: linear-gradient(to top, #430c86 0%, #391169 100%);
    position: absolute;
    left: 0;
    right: 0;
    margin: auto;
    top: 50%;
    @media (max-width: 640px) {
      width: 100px;
      height: 100px;
    }
  }
  .position-L {
    top: 5%;
    left: 20%;
    @media (max-width: 640px) {
      top: 10%;
      left: 10%;
    }
  }
  .position-R {
    top: 5%;
    right: 20%;
    @media (max-width: 640px) {
      top: 10%;
      right: 10%;
    }
  }
  .title {
    color: white;
    background: #d299c2;
    background: linear-gradient(0deg, #d299c2 0%, #fef9d7 100%);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
    font-size: 6rem;
    text-align: center;
    position: absolute;
    letter-spacing: 0.5rem;
    left: 0;
    right: 0;
    margin: auto;
    top: 30%;
    @media (max-width: 900px) {
      font-size: 2rem;
    }
    opacity: 0;
  }
</style>
