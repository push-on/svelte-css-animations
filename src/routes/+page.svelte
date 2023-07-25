<div class="container">
  <div>
    <h1>CSS Animations</h1>
    <a href="/particles">1. CSS particles Floating Up</a>
  </div>
</div>

<style lang="scss">
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    height: 100vh;
		padding: 5rem;
  }
  a {
    color: white;
    font-size: 1.5rem;
    &:hover {
      text-decoration: underline;
      text-underline-offset: 5px;
			text-decoration-color: darkgray;
    }
  }
  h1 {
    font-size: 5rem;
    font-family: "Segoe UI", Tahoma, Geneva, Verdana, sans-serif;
		font-weight: 100;
  }
</style>
