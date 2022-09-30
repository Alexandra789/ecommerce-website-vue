<template>
  <Header/>
</template>

<script>

import Header from "@/components/header/Header";

export default {
  components: {Header}
}
</script>

<style lang="scss">
* {
  font-family: Inter, serif;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

h1, h2, h3, h4, h5, h6, ul {
  padding: 0;
  margin: 0;
}

input, textarea, button {
  outline: none;
  border: none;
}

a, .logo__title, button {
  text-decoration: none;
  transition: .21s ease-in-out;
}

svg {
  path {
    transition: .21s ease-in-out;
  }
}
</style>
