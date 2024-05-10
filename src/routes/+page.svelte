<main class="container">
  <div>
    <h1>CSS <span>Animations</span></h1>
    <div class="links">
      <a href="/particles">1. CSS particles Floating Up</a>
      <a href="/scroll_animation">2. Scroll Animations</a>
    </div>
  </div>
</main>

<style lang="scss">
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    padding: 5rem;
  }

  .links {
    display: flex;
    flex-direction: column;
    gap: 0.5rem;
  }

  a {
    width: fit-content;
    padding-bottom: 1rem;
    color: white;
    font-size: 1.5rem;
    overflow: hidden;
    position: relative;
    display: inline-block;

    &::after {
      content: "";
      position: absolute;
      bottom: 0px;
      left: 0;
      width: 100%;
      height: 5px;
      background-color: rgb(98, 109, 255);
      transform: translate3d(0, 0, 0);
      transition: transform 1s cubic-bezier(0.34, 0.36, 0, 1.01);
    }

    &:hover {
      &::after {
        transform: translate3d(0, 0, 0);
      }
    }

    &:not(:hover) {
      &::after {
        transform: translate3d(-105%, 0, 0);
      }
    }
  }

  h1 {
    font-size: 5rem;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
    font-weight: 100;
    user-select: none;
  }
  span {
    font-weight: 400;
    background: linear-gradient(
      to right,
      rgba(111, 52, 255, 1) 0%,
      rgba(253, 60, 29, 1) 50%,
      rgba(111, 52, 255, 1) 100%
    );
    background-size: 200% auto;
    color: #000;
    background-clip: text;
    // text-fill-color: transparent;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: shine 3s linear infinite;
    @keyframes shine {
      to {
        background-position: 200% center;
      }
    }
  }
</style>
