<template>
  <div class="bag">
    <router-link class="ico-bag__wrap" to="/cart">
      <div class="counter">
        <p class="counter__num pt">{{ counter }}</p>
      </div>
      <div class="ico-bag__wrap">
        <img class="ico-bag__img" src="@/assets/graphics/bag.svg" alt="" />
        <div class="ico-bag__bg"></div>
      </div>
    </router-link>
  </div>
</template>

<script>
export default {
  computed: {
    counter() {
      let total = 0;
      this.$store.state.cart.map(item => (total += item.quantity));
      return total;
    }
  }
};
</script>

<style lang="scss">
@import "../scss/main";

.bag {
  position: absolute;
  z-index: 999;
  top: 20px;
  right: 20px;
}

.counter {
  width: 23px;
  height: 23px;
  background-color: $orange;
  border-radius: 50%;
  position: absolute;
  right: 0;

  &__num {
    color: white;
    margin-top: 1px;
    text-align: center;
    font-size: 12px;
  }
}

.ico-bag {
  &__wrap {
  }

  &__img {
    margin: 20px auto auto 20px;
    width: 20px;
    height: 20px;
    position: absolute;
  }

  &__bg {
    width: 60px;
    height: 60px;
    background-color: $brown;
    border-radius: 50%;
  }
}
</style>
