<template>
<div class="container">
<Select
:selected="selected"
:categories="categories"
@select="sortByCategories"
/>

        <div class="row">
<Shop />
<Cart v-for="(product, index) in filteredProducts"
:key="'product-' + index"
:product_data="product"
@AddToCart="AddToCart"
 class="col-md-3"
 />
</div>
</div>
</template>
<script>
import {mapActions, mapGetters, mapState} from 'vuex'
export default {
data(){
return{
categories:[
{name: 'All', value: 'all'},
{name: 'Birthday', value: 'b'},
{name: '8March', value: 'm'}
],
selected:'All',
sortedProducts: []
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
}),
filteredProducts(){
if (this.sortedProducts.length) {
return this.sortedProducts
} else {
return this.products
}
}
},

methods: {
...mapActions([
'ADD_TO_CART'
]),
AddToCart(data) {
this.ADD_TO_CART(data)
},
sortByCategories(category) {
this.sortedProducts = []
let vm = this
this.products.map(function (item) {
if (item.category === category.name) {
vm.sortedProducts.push(item)
}
})
}
}
}
</script>
