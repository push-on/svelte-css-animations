<script>
  import mountain_front from "../../assets/paralax/1.webp";
  import mountain_mid from "../../assets/paralax/2.webp";
  import mountain_back from "../../assets/paralax/3.webp";
</script>

<div class="wrapper">
  <header >
    <img class="forground_1 img" src={mountain_front} alt="" />
    <img class="forground_2 img" src={mountain_mid} alt="" />
    <img class="forground_3 img" src={mountain_back} alt="" />
    <h1 class="title">Parallax Scrolling</h1>
  </header>
</div>

<style lang="scss">
  .title {
    color: white;
    font-size: 6rem;
    text-shadow: 0 0 10px rgba(0, 0, 0, 0.5);
    font-weight: lighter;
    letter-spacing: 0.5rem;
    text-align: center;
    @media (max-width: 900px) {
      font-size: 3rem;
    }
  }
  .wrapper {
    height: 100vh;
    width: 100vw;
    overflow-y: auto;
    overflow-x: hidden;
    position: relative;
    perspective: 10px;
    background: rgb(0, 0, 0);
    background: linear-gradient(
      0deg,
      rgba(0, 0, 0, 1) 0%,
      rgb(31, 40, 64) 100%
    );
  }
  header {
    position: relative;
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    transform-style: preserve-3d;
    z-index: -1;
  }
  .img {
    position: absolute;
    transform-origin: top;
  }
  .forground_1 {
    z-index: -1;
    width: 100%;
    top: 50%;
  }
  .forground_2 {
    z-index: -2;
    width: 100%;
    top: 40%;
    transform: translateZ(-5px) scale(1.5);
  }
  .forground_3 {
    z-index: -3;
    width: 100%;
    top: 10%;
    transform: translateZ(-15px) scale(2.5);
  }
 
</style>
