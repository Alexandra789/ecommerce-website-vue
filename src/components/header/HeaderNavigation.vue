<template>
  <nav class="navigation">
    <ul class="navigation__menu">
      <li v-for="item in menuItems" :key="item.id" class="navigation__menu-item">
        <a href="#" class="navigation__menu-link"> {{ item.title }}</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "HeaderNavigation",
  props: {
    menuItems: {
      types: Array,
      required: true,
    }
  }
}
</script>

<style scoped lang="scss">
.navigation {
  &__menu {
    justify-content: space-between;
    display: flex;
    flex-wrap: wrap;
    margin: 0 24px;

    &-link {
      font-family: Quicksand, sans-serif;
      font-weight: 600;
      letter-spacing: .15px;
      font-size: 20px;
      text-decoration: none;
      color: $blue_color_menu_item;
      @media all and (max-width: 1020px) {
        font-size: 18px;
      }

      &:hover {
        color: $white;
      }
    }

    &-item {
      text-align: center;
      margin-right: 8px;
      min-width: 96px;
      @media all and (max-width: 1120px) {
        min-width: auto;
        margin-right: 16px;
      }

      &:last-child {
        margin-right: 0;
      }
    }
  }
}

</style>