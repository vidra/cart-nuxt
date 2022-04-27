<template>
<div>
<p>CartItem</p>
<CartItemItem
v-for="(item,index) in cart_data"
:key="'item-' + index"
:cart_item_data="item"
@DeleteFromCart="DeleteFromCart(index)"
@increment="increment(index)"
@decrement="decrement(index)"
/>

<div>Total:{{cartTotalCost}}</div>
</div>
</template>
<script>
import {mapActions} from 'vuex'

export default {
props: {
cart_data: {
type: Array,
default() {
return []
}
}
},
computed: {
cartTotalCost() {
let result = []
if (this.cart_data.length) {
for (let item of this.cart_data) {
result.push(item.price * item.quantity)
}
result = result.reduce(function (sum, el) {
return sum + el
})
return result
} else {
return 0
}
}
},

methods: {
...mapActions([
'DELETE_FROM_CART',
'INCREMENT_CART_ITEM',
'DECREMENT_CART_ITEM'

]),
increment(index) {
this.INCREMENT_CART_ITEM(index)
},
decrement(index) {
this.DECREMENT_CART_ITEM(index)
},

DeleteFromCart(index) {
this.DELETE_FROM_CART(index)
}
}
}
</script>
