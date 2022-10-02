<template>
  <button class="navigation-mobile-button" @click="openMenu">
    <svg class="navigation-mobile-button__icon" viewBox="0 0 20 20"
         xmlns="http://www.w3.org/2000/svg">
      <path fill="#fff" d="M11 16.5V13H3V7h8V3.5l6.5 6.5-6.5 6.5z"/>
    </svg>
  </button>
  <nav class="navigation close" ref="navigation">
    <svg xmlns="http://www.w3.org/2000/svg"
         class="close-navigation-menu-button" @click="closeMenu" viewBox="0 0 503.021 503.021">
      <path fill="white" d="M491.613,75.643l-64.235-64.235c-15.202-15.202-39.854-15.202-55.056,0L251.507,132.222L130.686,11.407
			c-15.202-15.202-39.853-15.202-55.055,0L11.401,75.643c-15.202,15.202-15.202,39.854,0,55.056l120.821,120.815L11.401,372.328
			c-15.202,15.202-15.202,39.854,0,55.056l64.235,64.229c15.202,15.202,39.854,15.202,55.056,0l120.815-120.814l120.822,120.814
			c15.202,15.202,39.854,15.202,55.056,0l64.235-64.229c15.202-15.202,15.202-39.854,0-55.056L370.793,251.514l120.82-120.815
			C506.815,115.49,506.815,90.845,491.613,75.643z"/>
    </svg>
    <ul class="navigation__menu">
      <li v-for="item in menuItems" :key="item.id" class="navigation__menu-item">
        <a href="#" class="navigation__menu-link"> {{ item.title }}</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: "HeaderNavigationAdaptive",
  props: {
    menuItems: {
      types: Array,
      required: true,
    }
  },
  methods: {
    openMenu() {
      this.$refs.navigation.classList.add('open');
      this.$refs.navigation.classList.remove('close');
      this.closeMenuClickByMainContent();
    },
    closeMenu() {
      this.$refs.navigation.classList.add('close');
      this.$refs.navigation.classList.remove('open');
    },
    closeMenuClickByMainContent() {
      document.addEventListener('click', (e) => {
        if (!(e.target.classList.value === 'navigation-mobile-button')
            && !(e.target.classList.value === 'navigation open')
            && !(e.target.classList.value === 'navigation__menu')
            && !(e.target.classList.value === 'navigation__menu-item')
        ) {
          this.closeMenu();
        }
      })
    }
  },
  mounted() {
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape') {
        this.closeMenu();
      }
    })
  }
}
</script>

<style scoped lang="scss">
.navigation-mobile-button {
  background-color: $blue_color_button;
  width: 60px;
  height: 60px;
  border-radius: 0 50% 50% 0;
  top: 50%;
  display: flex;
  align-items: center;
  position: fixed;

  &__icon {
    width: 40px;
    height: 40px;
  }

  &:before {
    content: "";
    position: absolute;
    z-index: 0;
    inset: 0;
    margin: auto;
    display: block;
    background: linear-gradient(45deg, $blue_color_background_header 15%, $blue_color_button 70%);
    border-radius: 0 50% 50% 0;
    -webkit-animation: pulse-border 1500ms ease-out infinite;
    animation: pulse-border 1500ms ease-out infinite;
  }

  &:after {
    content: "";
    position: absolute;
    z-index: 1;
    inset: 0;
    border-radius: 0 50% 50% 0;
    transition: all 200ms;
    box-shadow: 0 2px 7px #131b49;
  }

  @-webkit-keyframes pulse-border {
    0% {
      -webkit-transform: scale(1);
      transform: scale(1);
      opacity: 1;
    }
    100% {
      -webkit-transform: scale(1.5);
      transform: scale(1.5);
      opacity: 0;
    }
  }
  @keyframes pulse-border {
    0% {
      -webkit-transform: scale(1);
      transform: scale(1);
      opacity: 1;
    }

    100% {
      -webkit-transform: scale(1.5);
      transform: scale(1.5);
      opacity: 0;
    }
  }
}

.navigation {
  width: 60%;
  height: 100%;
  position: absolute;
  background: $blue_color_background_header;
  z-index: 5;
  border-radius: 0 16px 16px 0;
  top: 0;
  padding: 89px 32px 32px;
  text-align: center;

  .close-navigation-menu-button {
    right: 32px;
    width: 25px;
    height: 25px;
    top: 32px;
    position: absolute;

    &:hover {
      cursor: pointer;

      path {
        fill: $blue_color_menu_item;
      }
    }
  }

  &__menu {
    &-item {
      width: 100%;
      margin-bottom: 32px;

      &:last-child {
        margin-bottom: 0;
      }
    }

    &-link {
      color: $blue_color_menu_item;
      font-size: 40px;
      font-family: Quicksand, sans-serif;
      font-weight: 600;
      letter-spacing: .15px;

      &:hover {
        color: $white;
      }
    }
  }
}

.navigation.open {
  display: block;
}

.navigation.close {
  display: none;
}
</style>