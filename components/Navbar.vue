<template>
<div>
  <b-navbar toggleable="lg" type="light" variant="light" >
    <b-navbar-brand href="#">GingerBread.live</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#">About</b-nav-item>
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">


          <!-- Using 'button-content' slot -->
   <div> <b-icon-cart scale="1.5"  v-b-toggle.sidebar-right></b-icon-cart><span class="incart">{{CART.length}}</span></div>
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
<style>
.navbar{
background-color:#d8f4e2!important;
border-bottom:solid 0.2em #39b4ac;
}
.incart {
position: relative;
bottom:10px;
}
.incart {
padding-left: 0.3rem;
padding-right: 0.3rem;
background: #088178;
color:#fff;
border:solid 0.1em #d9eddb;
text-align: center;
display: inline;
border-radius: 50%;
}
</style>
