<template>
  <div>

    <b-sidebar id="sidebar-right" title="" right shadow>
      <div class="px-3 py-2">
<div>
<CartItem v-if="CART.length"
:cart_data="CART"
/>
</div>

      </div>
    </b-sidebar>
  </div>
</template>
<script>
import {mapGetters} from 'vuex'
export default {
computed: {
...mapGetters([
'CART'
])
}
}
</script>
