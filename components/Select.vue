<template>
<div class="select"
@click="areOptionsVisible = !areOptionsVisible"
>Category:
<span
class="options"
v-if="areOptionsVisible"
>
 <b-button pill variant="outline-secondary" v-for="category in categories" :key="category.value"
@click="selectOption(category)"
>
{{category.name}}
</b-button>


</span>
</div>
</template>
<script>
export default {
props:{
categories:{
type: Array,
default() {
return[]
}
},
selected: {
type: String,
default: ''
}
},
data() {
return{
areOptionsVisible: false
}
},
methods: {
selectOption(category) {
this.$emit('select', category)
}
}
}
</script>
<style>
.select{
padding: 15px;
}
</style>
