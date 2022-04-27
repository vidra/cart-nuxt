<template>
<div>
  <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#">NavBar</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#">Link</b-nav-item>
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">


          <!-- Using 'button-content' slot -->
    <b-button v-b-toggle.sidebar-right>Cart: {{CART.length}}</b-button>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
</div>

</template>

<script>
import {mapActions, mapGetters} from 'vuex'
export default {
computed: {
...mapGetters([
'CART'
])
},
}
</script>
