<template>
<div>
<div class="card mb-3" border-variant="success">
<div class="bg-image hover-overlay ripple" data-mdb-ripple-color="light">
 <a class="ripple" href="#!">
<img :src="product_data.photoURL" class="img-fluid rounded">

    </a>
</div>
 <div class="card-body">
  <small class="text-muted">{{product_data.description}}</small>

<h5>Name: {{product_data.name}}</h5>
<div class="row">

 <div class="col"><div class="product-price"> $ {{product_data.price}}</div></div>
<div class="col"></div>
<div style=" text-align: right" class="col"><span class="fa"><b-icon-cart-plus scale="1.5"  @click="AddToCart"></b-icon-cart-plus></span></div>
</div>
</div>
</div>
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
<style>
.product-price {
color:#088178;
font-size: 1.5em;
font-weight: bold;
}
.card{
border: solid 3px #cce7d0!important;
border-radius: 20px;

}

.card-body {
padding-top: 0rem!important;
padding-left: 1.25!important;
padding-right: 1.25rem!important;
}
.img-fluid{
border-radius: 20px!important;
padding: 7px;
}
.fa {background: #e8f6ea;
color:#088178;
border:solid 0.1em #d9eddb;
padding: 0.6em;
text-align: center;
display: inline;
border-radius: 50%;
}
</style>

