<template>
  <button  @click="toggleTheme" aria-label="Toggle themes">
    <span>Toggle Theme</span>  
  </button>
  <section aria-label="content">
      <Header />
      <main>
        <Contact />
      </main>
      <Footer />
    </section>
</template>

<script setup>
import Header from './components/Header.vue';
import Contact from './components/Contact.vue';
import Footer from './components/Footer.vue';
import { ref, onMounted } from 'vue';

const isDarkTheme = ref(false);

onMounted(() => {
  detectTheme();
})

const detectTheme = () => {
  // if media querry regarding dark theme matches, set var accordingly
  const darkThemeMq = window.matchMedia("(prefers-color-scheme: dark)");
  isDarkTheme.value = darkThemeMq.matches ? true : false;

  // if local storage has a mode set it should overrule the browser theme
  let localTheme = localStorage.getItem('isDarkTheme')
  if (localTheme != null) {
    isDarkTheme.value = localTheme == 'true' ? true : false;
  }
  applyTheme();
}

const toggleTheme = () => {
  isDarkTheme.value = isDarkTheme.value ? false : true;
  localStorage.setItem('isDarkTheme', isDarkTheme.value);
  applyTheme();
}

const applyTheme = () => {
  // update document accordingly
  if (isDarkTheme.value) {
    document.documentElement.setAttribute('data-theme', 'darkMode');
  } else {
    document.documentElement.setAttribute('data-theme', '');
  }
}
</script>

<style>
/* font import */
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@100;300;400&display=swap');

/* vars */
:root {
  --ui-border-radius: 15px;
  --background-image: url(./assets/bgday.jpg);
  --content-text-color: black;
  --content-arrowColor: black;

  --content-bg-color: #fffffffc;

  --footer-text-color: grey;
}

/* Variables for dark mode */
[data-theme="darkMode"] {
  --background-image: url(./assets/bgnight.jpg);
  --content-text-color: rgba(255, 255, 255, .87);
  --content-arrowColor: rgba(255, 255, 255, .87);

  --content-bg-color: #242424fc; /* #242424 */

  --footer-text-color: grey;
}


/* general stuff */
* {
  padding: 0;
  margin: 0;
}

html {
  height: 100%;
}

/* body */
body {
  /* font */
  font-family: 'Roboto', sans-serif;
  font-weight: 400;
  color: var(--content-text-color);
  /* background-color: aliceblue; */
  background-image: var(--background-image);
  background-size: 100%;
  height: 100%;

  /* Center and scale the image nicely */
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;

  /* transition */
  transition: all ease-in-out 0.2s;
}

h1 {
  font-size: 36px;
}

h2 {
  font-size: 26px;
}

h3 {
  font-size: 22px;
}

p {
  font-weight: 300;
}

a {
  color: var(--content-text-color);
  text-decoration: none;
}

/* content */
section {
  position: absolute;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  padding: 1rem;
  background-color: var(--content-bg-color);
  border-radius: var(--ui-border-radius);
}

header {
  padding-bottom: 1rem;
}

footer {
  margin-top: 2vh;
}
</style>
