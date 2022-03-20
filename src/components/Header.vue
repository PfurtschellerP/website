<script setup>
import { ref } from 'vue'

defineProps({
  msg: String
})

const count = ref(0)
</script>

<template>
<header>
  <img src="../assets/profileImage.jpeg" alt="profile picture"/>
  <div>
    <h1>Patrick Pfurtscheller</h1>
    <p>Personal Profile</p>
  </div>
</header>
</template>

<style scoped>
header {
  display: flex;
  flex-flow: row nowrap;
}

img {
  height: 14vh;
  width: auto;
  border-radius: 100%;
  margin-right: 1rem;
}

div {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
}
</style>
