<template>
  <div class="v-main-wrapper">
    <p>{{title}}</p>
    <v-catalog/>
    <v-cart
        v-if="CART.length"
        :cart_data="CART"
    />
  </div>
</template>

<script>
import vCatalog from './v-catalog'
import vCart from './v-cart'
import {mapActions, mapGetters} from 'vuex'
export default {
  name: 'v-main-wrapper',
  components: {
    vCatalog,
    vCart
  },
  props: {},
  data() {
    return {
      title: 'Main wrapper'
    }
  },
  computed: {
    ...mapGetters([
        'CART'
    ])
  },
  methods: {},
  watch: {}
}
</script>

<style>
.v-main-wrapper {
  margin: 0 auto;
}
</style>
