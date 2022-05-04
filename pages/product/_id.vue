<template>
<div>
<div>{{ product.description }}</div>
</div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  head() {
    return {
      title: this.product.name,
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'What you need to know about ' + this.product.name
        }
      ]
    }
  },
  async fetch({ store, error, params }) {
    try {
      await store.dispatch('products/fetchProduct', params.id)
    } catch (e) {
      error({
        statusCode: 503,
        message: 'Unable to fetch event #' + params.id
      })
    }
  },
  computed: mapState({
    product: state => state.products.product
  })
}
</script>
