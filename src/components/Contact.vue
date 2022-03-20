<template>
  <header>
    <h2>Contact</h2>
  </header>
  <main>
    <ContactOption v-for="option in options" :option="option" :key="option.title" />
  </main>
</template>

<script setup>
import ContactOption from './ContactOption.vue'
import { ref } from 'vue';

const options = ref([
  {
  title: "Email",
  imagePath: "email.png",
  subtitle: "Patrick@Pfurtscheller.org",
  link: "mailto://Patrick@Pfurtscheller.org"
  },
  {
  title: "LinkedIn",
  imagePath: "linkedin.png",
  subtitle: "Patrick Pfurtscheller",
  link: "https://www.linkedin.com/in/patrick-pfurtscheller/"
  },
  {
  title: "GitHub",
  imagePath: "github.png",
  subtitle: "PfurtschellerP",
  link: "https://github.com/PfurtschellerP"
  }
])

</script>

<style scoped>
main > div {
  margin-bottom: 1.5vh;
}
</style>