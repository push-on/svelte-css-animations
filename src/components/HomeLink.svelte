<a href="/">
  <span class="link-text">Home</span>
  <svg
    class="arrow"
    viewBox="0 0 24 24"
    fill="none"
    stroke="currentColor"
    stroke-width="2"
    stroke-linecap="round"
    stroke-linejoin="round">
    <path d="M14 5l7 7m0 0l-7 7m7-7H3" />
  </svg>
</a>

<style lang="scss">
  .link-text {
    margin-right: 0.5rem; // Add spacing between text and arrow
  }
  a {
    filter: drop-shadow(0 25px 25px rgb(0 0 0 / 0.15));
    background-color: rgb(2 6 23);
    text-decoration: none;
    font-weight: 600;
    position: fixed;
    top: 3rem;
    left: 3rem;
    padding: 1rem;
    border: 2px solid rgb(148 163 184);
    border-radius: 1rem;
    display: inline-flex;
    align-items: center;
    z-index: 1;
    .arrow {
      width: 1.5rem;
      transition: 0.3s;
      transform: translateX(0);
    }

    &:hover {
      .arrow {
        transform: translateX(10px);
      }
    }
    @media (max-width: 640px) {
      top: auto;
      left: 0.25rem;
      bottom: 0.25rem;
      font-size: small;
    }
  }
</style>
