<template>
  <div class="search-panel" ref="searchPanel">
    <svg class="search-panel__icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px"
         viewBox="0 0 487.95 487.95" xml:space="preserve">
		<path d="M481.8,453l-140-140.1c27.6-33.1,44.2-75.4,44.2-121.6C386,85.9,299.5,0.2,193.1,0.2S0,86,0,191.4s86.5,191.1,192.9,191.1
			c45.2,0,86.8-15.5,119.8-41.4l140.5,140.5c8.2,8.2,20.4,8.2,28.6,0C490,473.4,490,461.2,481.8,453z M41,191.4
			c0-82.8,68.2-150.1,151.9-150.1s151.9,67.3,151.9,150.1s-68.2,150.1-151.9,150.1S41,274.1,41,191.4z"/>
</svg>

    <input v-model="inputValue" @blur="blurSearchInput" @focus="focusSearchInput" type="text"
           class="search-panel__input"
           :placeholder="placeholder">
  </div>
</template>

<script>
export default {
  name: "HeaderSearchPanel",
  data() {
    return {
      inputValue: '',
      placeholder: 'Search',
    }
  },
  methods: {
    focusSearchInput() {
      this.$refs.searchPanel.classList.add('focused');
      this.placeholder = '';
    },
    blurSearchInput() {
      this.$refs.searchPanel.classList.remove('focused');
      this.placeholder = 'Search';
    },
  },
}
</script>

<style scoped lang="scss">
.search-panel {
  width: 192px;
  position: relative;
  height: 40px;
  border-radius: 50px;
  margin-right: 16px;
  @media (min-width: 669px) and (max-width: 992px) {
    width: 75%;
  }
  @media (min-width: 536px) and (max-width: 668px) {
    width: 65%;
  }
  @media all and (max-width: 536px) {
    width: 100%;
    margin-top: 16px;
    margin-right: 0;
  }
  //@media (min-width: 450px) and (max-width: 533px) {
  //  width: 50%;
  //}
  //@media (max-width: 450px) {
  //  display: none;
  //}


  &:hover {
    .search-panel__icon {
      path:last-child {
        fill: $blue_color_icon;
      }
    }
  }

  &__icon {
    width: 16px;
    height: 16px;
    position: absolute;
    fill: $gray_color_icon;
    top: 12px;
    left: 16px;
  }

  &__input {
    font-family: Roboto, serif;
    width: 100%;
    height: 100%;
    border-radius: 50px;
    border: none;
    padding: 8px 16px 8px 40px;
    outline: none;
    font-size: 14px;
    transition: .21s ease-in-out;
    color: $black_color_text;
  }

}

.search-panel.focused {
  .search-panel__icon {
    path:last-child {
      fill: $blue_color_icon;
    }
  }

  .search-panel__input {
    background: $blue_color_background;
  }
}
</style>