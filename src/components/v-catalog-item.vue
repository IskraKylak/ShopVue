<template>
  <div class="v-catalog-item">
    <img :src="require('@/assets/images/' + product_data.image)" alt="img">
    <p class="v-catalog-item_name">{{ product_data.name }}</p>
    <p class="v-catalog-item_price">Price: {{ product_data.price }}</p>
    <button class="v-catalog-item_add_to_cart_button btn" @click="addToCart">Add to cart</button>
  </div>
</template>

<script>

export default {
  name: 'v-catalog-item',
  props: {
    product_data: {
      type: Object,
      default() {
        return {}
      }
    }
  },
  data() {
    return {
      title: 'Main wrapper'
    }
  },
  computed: {},
  methods: {
    addToCart () {
      this.$emit('addToCart', this.product_data)
    }
  },
  watch: {}
}
</script>

<style lang="scss">
.v-catalog-item {
  flex-basis: 25%;
  box-shadow: 0 0 8px 0 #e0e0e0;
  padding: 10px;

  &__image {
    width: 100px;
  }
}
</style>
