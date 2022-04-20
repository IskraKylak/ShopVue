<template>
  <div class="v-cart-item'">
    <img :src="require('@/assets/images/' + cart_item_data.image)" alt="img">
    <p class="v-cart-item_name">{{ cart_item_data.name }}</p>
    <p class="v-cart-item_price">Price: {{ cart_item_data.price }}</p>
    <p class="v-cart-item_article">Article: {{ cart_item_data.article }}</p>
    <div class="v-cart-item__quantity">QTY:{{ cart_item_data.quantity }}</div>
    <button class="v-cart-item_remove_to_cart_button btn" @click="deleteFromCart">Delete</button>
  </div>

</template>

<script>

export default {
  name: 'v-cart-item',
  props: {
    cart_item_data: {
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
    deleteFromCart(index) {
      this.$emit('deleteFromCart')
    }
  },
  mounted() {
    this.cart_item_data.quantity =  1
  },
  watch: {}
}
</script>

<style lang="scss">
.v-cart-item {
  display: flex;
  flex-wrap: nowrap;
  justify-content: space-between;
  align-items: center;
  box-shadow: 0 0 8px 0 #e0e0e0;
  padding: 10px;
  margin-bottom: 10px;
  &__image {
    max-width: 50px;
  }

  .quantity__btn {
    cursor: pointer;
  }

  .quantity__tools {
    user-select: none;
  }
}
</style>
