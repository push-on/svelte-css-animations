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

<div class="container">
  <h1 class="title">MOTION ONE</h1>
  <div class="ball position-L"></div>
  <div class="ball position-R"></div>
  <div class="box"></div>
  <h1 class="glass">GLASS</h1>
</div>

<style lang="scss">
  .container {
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    overflow: hidden;
  }
  .glass {
    text-align: center;
    font-size: 5rem;
    position: absolute;
    color: rgba(0, 0, 0, 0.37);
    z-index: 1000;
    bottom: 60%;
    padding-left: 17rem;
    padding-right: 17rem;
    padding-top: 1.75rem;
    padding-bottom: 1.75rem;
    background: rgba(255, 255, 255, 0.05);
    border-radius: 16px;
    box-shadow: 0 4px 40px rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(20px);
    -webkit-backdrop-filter: blur(20px);
    border: 1px solid rgba(255, 255, 255, 0.47);
    @media (max-width: 640px) {
      padding-left: 2.5rem;
      padding-right: 2.5rem;
      padding-top: 1.75rem;
      padding-bottom: 1.75rem;
      backdrop-filter: blur(10px);
      -webkit-backdrop-filter: blur(10px);
    }
    @media (max-width: 400px) {
      font-size: 3rem;
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
    bottom: 10%;
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
    letter-spacing: 0.5rem;
    margin: auto;
    top: 30%;
    @media (max-width: 900px) {
      font-size: 2rem;
    }
    @media (max-width: 400px) {
      font-size: 1rem;
    }
    opacity: 0;
  }
</style>
