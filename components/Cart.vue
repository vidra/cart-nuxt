<template>
<div><button @click="AddOne">Add</button></div>

</template>
<script>
export default {
methods: {
AddOne() {
this.$store.commit('increment')
}
}
}
</script>

