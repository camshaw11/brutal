<script setup>
import HelloWorld from './components/HelloWorld.vue'
</script>

<template>
  <main>
    <div class="wrapper">
      <!-- <HelloWorld /> -->
      <div class="counter">0</div>
      <div class="overlay">
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
        <div class="bar"></div>
      </div>
    </div>

    <div class="container">
      <nav>
        <div>
          <a href="#"></a>
          <a href="#"></a>
        </div>
        <div>
          <a href="#"></a>
        </div>
      </nav>
    </div>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  main {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  main .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
