<script>
  import HomeLink from "../../components/HomeLink.svelte"
  import Mounitain_one from "../../assets/mountain_one.webp"
  import Mounitain_two from "../../assets/mountain_two.webp"
  import Mounitain_three from "../../assets/mountain_three.webp"
  import Mounitain_four from "../../assets/mountain_four.webp"
  import Mounitain_five from "../../assets/mountain_five.webp"
</script>

<div class="scroll_watcher" />
<HomeLink />
<main>
  <div class="hero">
    <div class="hero-content">
      <h1>CSS Only Scroll Driven Animations</h1>
      <p>
       supported on chromium based browsers only
      </p>
    </div>
  </div>

  <article class="content">
    <div>
      <h2>Lorem ipsum dolor sit amet</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Consectetur
        corrupti, totam nostrum fuga reprehenderit esse placeat itaque cumque
        veritatis facere reiciendis similique rerum qui dolorum possimus soluta
        aperiam. Quis, facere.
      </p>
      <img src={Mounitain_one} alt="" />
    </div>

    <div>
      <h2>Lorem ipsum dolor sit amet</h2>
      <p>
        Lorem ipsum dolor, sit amet consectetur adipisicing elit. Odit amet
        praesentium hic dicta iure, dolorem laudantium reprehenderit sit aliquam
        deleniti sequi consequuntur alias beatae blanditiis temporibus quisquam
        iste nam. Nobis?
      </p>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Sint minus
        quisquam et facilis excepturi nesciunt officia laudantium ad culpa ipsum
        consequatur soluta quis, aliquam atque magnam praesentium quasi, dolorem
        aspernatur. Corporis excepturi quae officia aliquam! Error sunt quisquam
        odit nesciunt alias qui. Suscipit quisquam consequatur, laudantium
        voluptatem labore, est, rerum harum accusantium rem sit nulla ex fugiat
        ad quam ipsam.
      </p>
      <img src={Mounitain_three} alt="" />
    </div>

    <div>
      <h2>Lorem ipsum dolor sit amet</h2>
      <p>
        Lorem ipsum dolor sit, amet consectetur adipisicing elit. Non,
        distinctio quas hic pariatur ullam impedit, nesciunt adipisci magni
        labore id consequuntur obcaecati repellat accusantium voluptatem nobis
        ducimus illo, veniam ad.
      </p>
      <img src={Mounitain_four} alt="" />
    </div>

    <div>
      <h2>Lorem ipsum dolor sit amet</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto delectus
        expedita officiis praesentium eum totam neque quisquam nihil nam
        aliquam. Modi illum tempora, voluptatem officiis aut minima. Laborum,
        temporibus nam?
      </p>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Totam magni,
        est molestiae velit delectus minima nam accusantium quaerat, ad ducimus
        expedita, iure reprehenderit cum repudiandae perspiciatis laudantium!
        Maxime, labore ducimus. Assumenda amet enim dolorem, dolore placeat
        aliquam alias sequi a! At voluptatem voluptatibus optio explicabo itaque
        illo deleniti amet cupiditate ipsa ipsum libero, nemo mollitia! Pariatur
        quae quo ipsum nemo! Veritatis, blanditiis, explicabo molestiae
        obcaecati aliquam vero laborum quam officia, quasi eaque non dignissimos
        similique. Ipsam quibusdam asperiores, recusandae repudiandae in culpa,
        earum inventore vero non eligendi distinctio velit impedit!
      </p>
      <img src={Mounitain_five} alt="" />
    </div>

    <div>
      <h2>Lorem ipsum dolor sit amet</h2>
      <p>
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto delectus
        expedita officiis praesentium eum totam neque quisquam nihil nam
        aliquam. Modi illum tempora, voluptatem officiis aut minima. Laborum,
        temporibus nam?
      </p>
      <p>
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Totam magni,
        est molestiae velit delectus minima nam accusantium quaerat, ad ducimus
        expedita, iure reprehenderit cum repudiandae perspiciatis laudantium!
        Maxime, labore ducimus. Assumenda amet enim dolorem, dolore placeat
        aliquam alias sequi a! At voluptatem voluptatibus optio explicabo itaque
        illo deleniti amet cupiditate ipsa ipsum libero, nemo mollitia! Pariatur
        quae quo ipsum nemo! Veritatis, blanditiis, explicabo molestiae
        obcaecati aliquam vero laborum quam officia, quasi eaque non dignissimos
        similique. Ipsam quibusdam asperiores, recusandae repudiandae in culpa,
        earum inventore vero non eligendi distinctio velit impedit!
      </p>
      <img src={Mounitain_two} alt="" />
    </div>
  </article>
  <div class="space"/>
</main>

<style lang="scss">
  .space{
    height: 20vh;
  }
  .scroll_watcher {
    height: 2px;
    position: fixed;
    bottom: 1px;
    z-index: 1000;
    background-color: #4158d0;
    width: 100%;
    scale: 0 1;
    animation: scroll-watcher linear;
    animation-timeline: scroll();
    transform-origin: left;
  }
  @keyframes scroll-watcher {
    to {
      scale: 1 1;
    }
  }

  .hero {
    background-image: url("../../assets/mountain_two.webp");
    background-size: cover;
    background-position: center;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    width: 100vw;
    .hero-content {
      text-align: center;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5);

      h1 {
        font-size: 6rem;
        font-weight: lighter;
        text-wrap: balance;
        text-align: center;
        max-width: 75%;
        margin-left: auto;
        margin-right: auto;
        @media (max-width: 640px) {
          font-size: 3rem;
        }
      }
    }
  }
  article > div > img {
    animation: fade-in 1s ease-in-out;
    animation-timeline: view(700px 0px);
  }

  @keyframes fade-in {
    from {
      scale: 0.8;
      opacity: 0;
    }
    to {
      scale: 1;
      opacity: 1;
    }
  }
  .content {
    max-width: 900px;
    margin: 0 auto;
    padding: 2rem;
    display: flex;
    flex-direction: column;
    gap: 1.5rem;
  }
  h2 {
    font-size: 3rem;
    line-height: 1;
    margin-bottom: 1rem;
    @media (max-width: 640px) {
      font-weight: 500;
      font-size: 1.5rem;
    }
  }

  p {
    color: rgb(203 213 225);
    margin: 0;
    font-family: "Open Sans", sans-serif;
    font-size: 1rem;
    line-height: 1.5;
    margin-bottom: 2rem;
    @media (max-width: 640px) {
      font-size: 0.8rem;
    }
  }

  img {
    border-radius: 1rem;
    max-width: 100%;
    height: auto;
    margin-bottom: 1rem;
    box-shadow: 0 15px 40px -12px rgb(0 0 0);
    border: 1px solid rgb(41, 41, 41);
  }
</style>
