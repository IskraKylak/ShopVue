<template>
  <div class="v-catalog">
    <h1>Catalog</h1>
    <div class="catalog_list">
      <v-catalog-item
          v-for="product in PRODUCTS"
          :key="product.article"
          :product_data="product"
          @addToCart="addToCart"
      />
    </div>

  </div>
</template>

<script>
import vCatalogItem from './v-catalog-item'
import {mapActions, mapGetters} from 'vuex'
export default {
  name: 'v-catalog',
  components: {
    vCatalogItem,
  },
  props: {},
  data() {
    return {
      products: []
    }
  },
  computed: {
    ...mapGetters([
        'PRODUCTS'
    ])
  },
  methods: {
    ...mapActions([
        'GET_PRODUCTS_FROM_API',
        'ADD_TO_CART'
    ]),
    addToCart( data ) {
      this.ADD_TO_CART(data)
    }
  },
  mounted() {
    this.GET_PRODUCTS_FROM_API()
  },
  watch: {}
}
</script>

<style lang="scss">
.catalog_list {
  display: flex;
  grid-gap: 10px;
}
</style>
