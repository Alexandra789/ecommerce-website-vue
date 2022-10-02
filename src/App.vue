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

input, textarea, button {
  outline: none;
  border: none;
}

a, .logo__title, button {
  text-decoration: none;
  transition: .21s ease-in-out;
}

ul {
  list-style: none;
}

svg {
  path {
    transition: .21s ease-in-out;
  }
}

button {
  background-color: $blue_color_button;

  &:hover {
    cursor: pointer;
    background-color: $blue_color_button_hover;
  }
}
</style>
