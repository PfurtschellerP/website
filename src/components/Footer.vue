<template>
  <footer>
    <p>Icons from <a href="https://www.flaticon.com/" title="icons" target="_blank">Flaticon</a></p>
    <p>&copy;Patrick Pfurtscheller {{ new Date().getFullYear()}}</p>
  </footer>
</template>

<style scoped>
footer {
  display: flex;
  flex-flow: row wrap;
  justify-content: space-between;
}

a, p {
  color: var(--footer-text-color);
}
</style>