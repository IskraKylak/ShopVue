<template>
  <div>
    <h2>Cart</h2>
    <div class="cart-list">
      <v-cart-item
          v-for="(item, index) in cart_data"
          :key="item.article"
          :cart_item_data="item"
          @deleteFromCart="deleteFromCart(index)"
      />
    </div>


  </div>
</template>

<script>
import vCartItem from './v-cart-item'
import {mapActions, mapGetters} from 'vuex'
export default {
  name: 'v-cart',
  components: {
    vCartItem,
  },
  props: {
    cart_data: {
      type: Array,
      default() {
        return []
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
    ...mapActions([
      'DELETE_FROM_CART'
    ]),
    deleteFromCart(index) {
      this.DELETE_FROM_CART(index)
    }
  },
  watch: {}
}
</script>

<style>
.cart-list {
  display: flex;
  grid-gap: 10px;
}
</style>
