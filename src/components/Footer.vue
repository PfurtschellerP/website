<template>
  <footer>
    <p><a href="https://www.flaticon.com/" title="icons" target="_blank">Icons</a>; <a href="https://codepen.io/ahmadbassamemran/pen/yLBXBmy" title="toggle switch source" target="_blank">Toggle Switch</a></p>
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