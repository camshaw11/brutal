<script setup>
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
    duration: 1.3,
    delay: 3.5,
    height: 0,
    stagger: {
      each: 0.1,
    },
    ease: "power4.inOut",
  });

  gsap.from(".h1", {
    duration: 1.5,
    delay: 3,
    y: 900,
    stagger: {
      each: 0.3,
    },
    ease: "power4.inOut",
  });

  gsap.from(".hero", {
    duration: 2,
    delay: 4,
    y: 900,
    ease: "power4.inOut",
  });
});

</script>

<template>
  <main>
    <!-- <HelloWorld /> -->
    <div class="wrapper">
      <nav>
        <div>
          <p>cameronshaw95@gmail.com</p>
          <a href="#">NZ</a>
        </div>
        <div>
          <a href="#">front end developer</a>
        </div>
      </nav>
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
        <div class="h1">C</div>
        <div class="h1">A</div>
        <div class="h1">M</div>
        <div class="h1">E</div>
        <div class="h1">R</div>
        <div class="h1">O</div>
        <div class="h1">N</div>
        <div class="h1">.</div>
      </div>
      <div class="description">
        <p>A quick static website I created so I could submit something into the google form.
           I am a front end developer looking for work / keen to help out on some <b>cool</b> projects. I am from New Zealand, currently in Belgium EU for a while :).
        </p>
        <br>
        <p>I've been a big fan of the content produced for Skrillex for a long time - love the work especially from Marilyn & Jas</p>
      </div>
      <div class="hero">
        <img src="./assets/me.jpg" alt="hero image">
      </div>
      <div class="footer">
        <div class="h1">E</div>
        <div class="h1">M</div>
        <div class="h1">A</div>
        <div class="h1">I</div>
        <div class="h1">L</div>        
        <div class="h1">M</div>
        <div class="h1">E</div>
        <div class="h1">.</div>
      </div>
    </div>
  </main>
</template>

<style scoped>
@import url('https://fonts.cdnfonts.com/css/lt-binary-neue');
@import url('https://fonts.cdnfonts.com/css/socilo');

.header .h1 {
  position: relative;
  font-family: 'Socilo', sans-serif;
  font-size: 12em;
  line-height: 1.5;
  color: #1a1a1a;
}

.footer .h1 {
  position: relative;
  font-family: 'Socilo', sans-serif;
  font-size: 12em;
  line-height: 1.5;
  color: #1a1a1a;
}

.description {
  padding: 2em;
}

p {
  font-family: 'LT Binary Neue', sans-serif;
}
/* Apply responsive font size using viewport width */
@media screen and (max-width: 968px) {
  .header .h1 {
    font-size: 12vw;
    line-height: 1.8;
  }

  .footer .h1 {
    font-size: 12vw;
    line-height: 1.8;
  }
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
  font-family: 'Socilo', sans-serif;
}

.hero {
  position: relative;
  width: calc(100vw - 4em);
  height: 100%;
  margin: 0 auto;
  border-radius: 10px;
}
</style>
