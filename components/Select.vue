<template>
<div class="select">
<p class="title"
@click="areOptionsVisible = !areOptionsVisible"
>Select</p>
<div
class="options"
v-if="areOptionsVisible"
>
<p v-for="category in categories" :key="category.value"
@click="selectOption(category)"
>

{{category.name}}
</p>
</div>
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
position:relative;
width: 200px;
cursor: pointer;
}
.title{
border: solid 1px #000;
}
.select p{
margin:0;
}
.options {
border: solid 1px #000;
position: absolute;
top: 30px;
right: 0;
width: 100%;
}
.options p:hover{
background: #e7e7e7;
}
</style>
