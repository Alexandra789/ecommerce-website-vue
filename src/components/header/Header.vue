<template>
  <div class="header">
    <a href="#" class="logo">
      <img src="@/assets/images/logo.png" alt="logo img" class="logo__img">
      <h1 class="logo__title">ShopPage</h1>
    </a>
    <HeaderNavigation :menuItems="menuItems"/>
    <div class="user-information">
      <HeaderSearchPanel v-if="widthWindow>536"/>
      <HeaderBasketProducts/>
      <HeaderUserProfile/>
    </div>
    <HeaderSearchPanel v-if="widthWindow<=536"/>
  </div>
</template>

<script>
import HeaderNavigation from "@/components/header/HeaderNavigation";
import HeaderSearchPanel from "@/components/header/HeaderSearchPanel";
import HeaderBasketProducts from "@/components/header/HeaderBasketProducts";
import HeaderUserProfile from "@/components/header/HeaderUserProfile";

export default {
  name: "Header",
  components: {HeaderUserProfile, HeaderSearchPanel, HeaderNavigation, HeaderBasketProducts},
  data() {
    return {
      menuItems: [
        {id: 1, title: 'New in'},
        {id: 2, title: 'Clothing'},
        {id: 3, title: 'Shoes'},
        {id: 4, title: 'Accessories'},
        {id: 5, title: 'More'},
      ],
      widthWindow: window.innerWidth,
    }
  },
  mounted() {
    window.onresize = () => {
      return (() => {
        window.screenWidth = window.innerWidth;
        this.widthWindow = window.screenWidth;
        this.widthWindow === 535 ? this.myFlexWrap = 'wrap' : this.myFlexWrap = 'none';
      })()
    }
  }
}
</script>

<style scoped lang="scss">
.header {
  color: white;
  display: flex;
  flex: 1 1 auto;
  justify-content: space-between;
  align-items: center;
  padding: 12px 16px;
  background: $blue_color_background_header;
  box-shadow: 0 1px 2px #9dc2ff, 0 2px 4px #c4daff;
  @media all and (max-width: 536px) {
    flex-wrap: wrap;
  }

  .logo {
    display: flex;
    align-items: center;
    margin-right: 16px;

    &:hover {
      .logo__title {
        color: $blue_color_menu_item;
      }
    }

    &__title {
      font-size: 24px;
      color: $white;
      font-weight: 500;
      @media all and (max-width: 480px) {
        font-size: 22px;
      }
    }

    &__img {
      width: 40px;
      height: 40px;
      margin-right: 24px;
      @media all and (max-width: 700px) {
        margin-right: 8px;
      }
      @media all and (max-width: 480px) {
        width: 30px;
        height: 30px;
      }
    }
  }

  .user-information {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    max-width: 310px;
    width: 100%;
    @media all and (max-width: 536px) {
      max-width: 100px;
      justify-content: flex-end;
    }
    @media (min-width: 537px) and (max-width: 992px) {
      max-width: 450px;
      justify-content: flex-end;
    }
  }
}
</style>