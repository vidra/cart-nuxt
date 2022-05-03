<template>
<div>
 <img :src="cart_item_data.photoURL" class="card-img-top">
<p>{{cart_item_data.name}}</p>
<p>{{cart_item_data.price}}</p>
<span><span @click="decrementItem">-</span>{{cart_item_data.quantity}}<span @click="incrementItem">+</span></span>
<button @click="DeleteFromCart">Delete</button>
</div>
</template>
<script>
import {mapActions} from 'vuex'
export default {
props: {
cart_item_data:{
type: Object,
default() {
return{}
}
}

},
data() {
return{}
},
computed: {},
mounted() {
},
methods: {

DeleteFromCart(){
this.$emit('DeleteFromCart')
},
decrementItem(){
this.$emit('decrement')
},
incrementItem(){
this.$emit('increment')
}
}

}

</script>
