<template>
<div>
      <table class="table">
            <tbody>
              <tr>
                <th scope="row">
                  <div class="d-flex align-items-center">
                    <img :src="cart_item_data.photoURL" class="img-fluid rounded-3"
                      style="width: 100px;" alt="Book">
                    <div class="flex-column ms-4">
                    </div>
                  </div>
                </th>
                <td class="align-middle">
                  <div class="d-flex flex-row">
<span><span @click="decrementItem">-</span>{{cart_item_data.quantity}}<span @click="incrementItem">+</span></span>

                  </div>
                </td>
                <td class="align-middle">
{{cart_item_data.price}}
                </td>
<td class="align-middle">
<b-icon-trash-fill @click="DeleteFromCart"></b-icon-trash-fill>

</td>

              </tr>
</tbody>
          </table>
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
<style>
.table {
cellpadding:0;
 cellspacing:0
}
.table tr{
border-bottom: 1px solid #dee2e6;
}
</style>

