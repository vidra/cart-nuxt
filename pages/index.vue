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
import {mapActions, mapGetters} from 'vuex'
export default {
data(){
return{
products:[
{
uuid: '344-33-20',
name: 'Camera0',
description: 'Lorem ipsum dolor sit amet',
price: 950,
photoURL: 'https://mykaleidoscope.ru/uploads/posts/2021-09/1632934645_30-mykaleidoscope-ru-p-rospis-pryanikov-glazuryu-master-krasivo-f-30.jpg',
quantity: 1
},
{
uuid: '344-33-21',
name: 'Camera1',
description: 'Lorem ipsum dolor sit amet',
price: 950,
photoURL: 'https://mykaleidoscope.ru/uploads/posts/2021-09/1632934645_30-mykaleidoscope-ru-p-rospis-pryanikov-glazuryu-master-krasivo-f-30.jpg',
quantity: 1
},
{
uuid: '344-33-22',
name: 'Camera2',
description: 'Lorem ipsum dolor sit amet',
price: 950,
photoURL: 'https://mykaleidoscope.ru/uploads/posts/2021-09/1632934645_30-mykaleidoscope-ru-p-rospis-pryanikov-glazuryu-master-krasivo-f-30.jpg',
quantity: 1
}


],
}
},
computed: {
...mapGetters([
'CART'
])
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
