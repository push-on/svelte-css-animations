<script>
  import HomeLink from "../../components/HomeLink.svelte"
</script>

<!-- PARTICLE SYSTEM -->
<main>
  <HomeLink />

  <div class="page-bg" />

  <div class="animation-wrapper">
    <div class="particle particle-1" />
    <div class="particle particle-2" />
    <div class="particle particle-3" />
    <div class="particle particle-4" />
  </div>
</main>

<style lang="scss">
  /* Config */
  @use "sass:math";

  $color-bg: #111;
  $color-particle: #fff;
  $spacing: 2560px;
  $time-1: 60s;
  $time-2: 120s;
  $time-3: 180s;
  $time-4: 600s;

  @function particles($max) {
    $val: 0px 0px $color-particle;
    @for $i from 1 through $max {
      $val:
        #{$val},
        math.random($spacing) + px math.random($spacing) + px $color-particle;
    }
    @return $val;
  }

  @mixin particles($max) {
    box-shadow: particles($max);
  }

  /* Styles */
  main {
    position: fixed;
  }

  .particle,
  .particle:after {
    background: transparent;
  }

  .particle:after {
    position: absolute;
    content: "";
    top: $spacing;
  }

  .particle-1 {
    animation: animParticle $time-1 linear infinite;
    @include particles(600);
    height: 1px;
    width: 1px;
  }

  .particle-1:after {
    @include particles(600);
    height: 1px;
    width: 1px;
  }

  .particle-2 {
    animation: animParticle $time-2 linear infinite;
    @include particles(200);
    height: 2px;
    width: 2px;
  }

  .particle-2:after {
    @include particles(200);
    height: 2px;
    width: 2px;
  }

  .particle-3 {
    animation: animParticle $time-3 linear infinite;
    @include particles(100);
    height: 3px;
    width: 3px;
  }

  .particle-3:after {
    @include particles(100);
    height: 3px;
    width: 3px;
  }

  .particle-4 {
    animation: animParticle $time-4 linear infinite;
    @include particles(400);
    height: 1px;
    width: 1px;
  }

  .particle-4:after {
    @include particles(400);
    height: 1px;
    width: 1px;
  }

  @keyframes animParticle {
    from {
      transform: translateY(0px);
    }
    to {
      transform: translateY($spacing * -1);
    }
  }
</style>
