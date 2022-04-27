<template>
<div>
<div class="card mb-3">

<img :src="product_data.photoURL" class="card-img-top">
 <div class="card-body">
                        <h5 class="card-title">
<p>Name: {{product_data.name}}</p>
</h5>
<p>Price: {{product_data.price}}</p>
</div>

   <div class="d-grid"><button @click="AddToCart" class="btn btn-outline-primary">AddProduct</button></div>
<div><button @click="AddOne">Add</button></div>
</div></div>
</template>
<script>
export default {
props:{
product_data: {
type: Object,
default() {
return{}
}
}
},

methods: {
AddToCart() {
this.$emit('AddToCart', this.product_data)
},
AddOne() {
this.$store.commit('increment')
}
}
}
</script>

