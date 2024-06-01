<script>
  import { onMount } from "svelte";
  
  const links = [
    { href: "/particles", text: "CSS particles Floating Up" },
    { href: "/scroll_animation", text: "CSS only Scroll Animations" },
    { href: "/observer", text: "JS IntersectionObserver Animations" },
    { href: "/paralax_scrolling", text: "Parallax scrolling" },
    { href: "/motion", text: "Motion One Translate" },
    { href: "/motion_offset", text: "Motion offset" },
    { href: "/Grid_Animation", text: "Grid Animations" }
  ];

  let cursorBoxVisible = false;
  let cursorBoxPosition = { top: 0, left: 0 };
  let cursorBoxContent = "";

  function handleMouseEnter(event, text) {
    cursorBoxContent = "img preview: " + text  ;
    cursorBoxVisible = true;
    updateCursorBoxPosition(event);
  }

  function handleMouseLeave() {
    cursorBoxVisible = false;
  }

  function updateCursorBoxPosition(event) {
    cursorBoxPosition = { top: event.clientY + -50 + "px", left: event.clientX + -40 + "px" };
  }

  onMount(() => {
    window.addEventListener("mousemove", updateCursorBoxPosition);
    return () => {
      window.removeEventListener("mousemove", updateCursorBoxPosition);
    };
  });
</script>

<main class="container">
  <div>
    <h1>Web <span>Animations</span></h1>
    <ul class="links">
      {#each links as link, index}
        <li>
          <a href={link.href}
             on:mouseenter={(e) => handleMouseEnter(e, link.text)}
             on:mouseleave={handleMouseLeave}>
             {index + 1}. {link.text}
          </a>
        </li>
      {/each}
    </ul>
  </div>
  {#if cursorBoxVisible}
    <div class="cursor-box" style="top: {cursorBoxPosition.top}; left: {cursorBoxPosition.left};">
      {cursorBoxContent}
    </div>
  {/if}
</main>

<style lang="scss">
  $primary-color: rgb(199, 210, 254);
  $hover-color: rgb(241, 245, 249);
  $accent-color: rgb(98, 109, 255);
  $gradient: linear-gradient(
    to right,
    rgba(111, 52, 255, 1) 0%,
    rgba(253, 60, 29, 1) 50%,
    rgba(111, 52, 255, 1) 100%
  );
  $font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
  $font-size-large: 5rem;
  $font-size-medium: 3rem;
  $link-font-size: 1.5rem;
  $transition-duration: 500ms;

  @mixin transition($property, $duration, $timing) {
    transition: $property $duration $timing;
  }

  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
    padding: 5rem;
  }

  .links {
    list-style: none;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 0.5rem;

    a {
      display: inline-block;
      position: relative;
      color: $primary-color;
      font-size: $link-font-size;
      text-wrap: nowrap;
      overflow: hidden;
      padding-bottom: 1rem;
      @include transition(color, $transition-duration, ease-in-out);

      &::after {
        content: "";
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 5px;
        background-color: $accent-color;
        transform: translate3d(-105%, 0, 0);
        @include transition(transform, 1s, cubic-bezier(0.34, 0.36, 0, 1.01));
      }

      &:hover {
        color: $hover-color;

        &::after {
          transform: translate3d(0, 0, 0);
        }
      }
    }
  }

  h1 {
    font-size: $font-size-large;
    font-family: $font-family;
    font-weight: 100;
    user-select: none;
    text-wrap: nowrap;

    @media (max-width: 640px) {
      font-size: $font-size-medium;
    }
  }

  span {
    font-weight: 400;
    background: $gradient;
    background-size: 200% auto;
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    animation: shine 3s linear infinite;

    @keyframes shine {
      to {
        background-position: 200% center;
      }
    }
  }

  .cursor-box {
    position: fixed;
    padding-left: 1.25rem;
    padding-right: 1.25rem;
    padding-top: 0.5rem;
    padding-bottom: 0.5rem;
    background-color: rgba(250, 250, 250, 0.271);
    color: white;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    border-radius: 8px;
    pointer-events: none;
    transition: opacity 0.3s, transform 0.3s;
    opacity: 1;
    backdrop-filter: blur(5px);
  }
</style>
