<script setup>
import HelloWorld from './components/HelloWorld.vue'
import { gsap } from 'gsap';

import { ref, onMounted } from 'vue';

const counterValue = ref(0);

const updateCounter = () => {
  if (counterValue.value === 100) {
    return;
  }

  counterValue.value += Math.floor(Math.random() * 10) + 1;

  if (counterValue.value > 100) {
    counterValue.value = 100;
  }

  let delay = Math.floor(Math.random() * 200) + 50;
  setTimeout(updateCounter, delay);
};

onMounted(() => {
  updateCounter(); // Initialize the loader after the component is mounted

  gsap.to(".counter", {
    duration: 0.25,
    delay: 3.5,
    opacity: 0,
  });

  gsap.to(".bar", {
    duration: 1.5,
    delay: 3.5,
    height: 0,
    stagger: {
      each: 0.5,
    },
    ease: "power4.inOut",
  });

  gsap.from(".h1", {
    duration: 1.5,
    delay: 4,
    y: 700,
    stagger: {
      each: 0.5,
    },
    ease: "power4.inOut",
  });

  gsap.from(".hero", {
    duration: 2,
    delay: 4.5,
    y: 400,
    ease: "power4.inOut",
  });
});

</script>

<template>
  <main>
    <HelloWorld />
    <div class="wrapper">
      <div class="counter">{{ counterValue }}</div>
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
      <div class="header">
        <div class="h1">U</div>
        <div class="h1">P</div>
        <div class="h1">G</div>
        <div class="h1">R</div>
        <div class="h1">A</div>
        <div class="h1">D</div>
        <div class="h1">E</div>
        <div class="h1">.</div>
      </div>
      <div class="hero">
        <!-- <img src="./assets/test.png" alt="hero image"> -->
      </div>
    </div>
  </main>
</template>

<style scoped>
@import url('https://fonts.cdnfonts.com/css/cherry-bomb-one');
                

.header .h1 {
  position: relative;
  font-family: 'Cherry Bomb One', sans-serif;
  font-size: 12em;
  line-height: 1.1;
  color: black;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.overlay {
  position: fixed;
  width: 100vw;
  height: 100vh;
  z-index: 2;
  display: flex;
}

.bar {
  width: 10vw;
  height: 105vh;
  background: lightcoral;
}

.counter {
  position: fixed;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: flex-end;
  align-items: flex-end;
  z-index: 1000;
  color:aliceblue;
  padding: 0.2em 0.4em;
  font-size: 12em;
  font-family: 'Cherry Bomb One', sans-serif;
}
</style>
