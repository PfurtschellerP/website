<template>
  <div id="option" :class="option.style" @click="redirectUser(option.link)">
    <img :src="option.imagePath" class="contactIcon"/>
    <div class="optionText">
      <h3>{{ option.title }}</h3>
      <p>{{ option.subtitle }}</p>
    </div>
  </div>
</template>

<script setup>

defineProps(['option'])

function redirectUser(url) {
  window.open(url);
}
</script>

<style scoped>
#option {
  padding: 0.8rem;
  border-radius: var(--ui-border-radius);
  display: flex;
  flex-flow: row nowrap;
  box-shadow: 2px 0px 10px 2px rgba(0,0,0,0.2);
  color: var(--content-text-color);
}

.optionText::after {
  content: "";
  width: 1.5em;
  height: 1.5em;
  border-top: solid 3px var(--content-arrowColor);
  border-right: solid 3px var(--content-arrowColor);
  display: inline;
  position: absolute;
  right: 2em;
  transform: rotate(45deg);
}

#option:hover {
  cursor: pointer;
  box-shadow: 2px 0px 10px 7px rgba(0,0,0,0.2);
}

img {
  height: 5vh;
  width: auto;
  margin-right: 0.75rem;
}

.optionText {
  display: flex;
  flex-flow: column nowrap;
  justify-content: center;
}
</style>