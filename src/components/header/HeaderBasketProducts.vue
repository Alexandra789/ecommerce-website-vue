<template>
  <a href="#" class="basket-product-button">
    <svg class="basket-product__icon" xmlns="http://www.w3.org/2000/svg" x="0px" y="0px"
         viewBox="0 0 482.854 482.854" xml:space="preserve">
		<path fill="white" d="M439.927,148.655h-21.5h-0.1h-9.5l-130.2-144.7c-4.4-4.9-12-5.3-16.9-0.9s-5.3,12-0.9,16.9l115.8,128.7h-269.9
			l115.4-128.7c4.4-4.9,4-12.5-0.9-16.9s-12.5-4-16.9,0.9l-129.9,144.7h-9.6l0,0h-21.9c-6.6,0-12,5.4-12,12s5.4,12,12,12h12.3
			l34.6,161.3c5.5,27.7,30,47.8,58.3,47.8h131.1c6.6,0,12-5.4,12-12s-5.4-12-12-12h-131.1c-16.9,0-31.5-12-34.8-28.6
			c0-0.1,0-0.1,0-0.2l-33.5-156.3h323.9l-13.8,67.6c-1.3,6.5,2.9,12.8,9.4,14.2c0.8,0.2,1.6,0.2,2.4,0.2c5.6,0,10.6-3.9,11.7-9.6
			l14.8-72.4h11.7c6.6,0,12-5.4,12-12S446.527,148.655,439.927,148.655z"/>
      <path fill="white" d="M380.327,357.155h-31.3c-12.3,0-22.3-10-22.3-22.3s10-22.3,22.3-22.3h55.1c6.6,0,12-5.4,12-12s-5.4-12-12-12h-27.5v-20.7
			c0-6.6-5.4-12-12-12s-12,5.4-12,12v20.7h-3.6c-25.5,0-46.3,20.8-46.3,46.3s20.8,46.3,46.3,46.3h31.3c12.3,0,22.3,10,22.3,22.3
			s-10,22.3-22.3,22.3h-56.2c-6.6,0-12,5.4-12,12s5.4,12,12,12h28.5v21.1c0,6.6,5.4,12,12,12s12-5.4,12-12v-21.1h3.9
			c0.1,0,0.2,0,0.3,0c25.2-0.3,45.6-21,45.6-46.3C426.527,377.855,405.827,357.155,380.327,357.155z"/>
    </svg>
    <span v-if="productCount>0" class="product-count-wrapper">
     {{ productCount }}
    </span>
  </a>
</template>

<script>
export default {
  name: "HeaderBucketProducts",
  data() {
    return {
      productCount: 3,
    }
  }
}
</script>

<style scoped lang="scss">
.basket-product-button {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  display: flex;
  justify-content: center;
  align-items: center;
  background: $blue_color_button;
  position: relative;
  margin-right: 16px;

  &:hover {
    background: $blue_color_button_hover;
  }

  .product-count-wrapper {
    position: absolute;
    right: 0;
    top: 0;
    background: $red;
    border-radius: 50%;
    width: 20px;
    height: 20px;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: Quaskand, sans-serif;
    font-size: 14px;
    color: $white;
    font-weight: 600;
  }

  svg {
    width: 24px;
    height: 24px;
  }
}
</style>