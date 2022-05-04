<template>
<div class="container">
        <div class="row">
<Shop />
<Cart v-for="(product, index) in products"
:key="'product-' + index"
:product_data="product"
@AddToCart="AddToCart"
 class="col-md-4"
 />
</div>
 </div>

</template>
<script>
import {mapActions, mapGetters, mapState} from 'vuex'
export default {
data(){
return{
}
},
async fetch({ store, error }) {
    try {
      await store.dispatch('products/fetchProducts')
    } catch (e) {
      error({
        statusCode: 503,
        message: 'Unable to fetch events at this time. Please try again.'
      })
    }
  },
computed: {
...mapGetters([
'CART'
]),
...mapState({
products: state => state.products.products
})
},

methods: {
...mapActions([
'ADD_TO_CART'
]),
AddToCart(data) {
this.ADD_TO_CART(data)
}
}
}
</script>
