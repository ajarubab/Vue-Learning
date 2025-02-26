<template>
    <h1>My Fourth Home</h1>
    <h2>Use of Non-Props for Data Passing</h2>
    <h3>{{ someData }}</h3>
    <div v-bind="$attrs">
        <h2>Apple</h2>
        <h2>Mango</h2>
        <h2 v-bind="$attrs" >Banana</h2>
        <h2>{{ someData }}</h2>
    </div>
</template>
<script>
export default{
    name : "MyFourthHome",
    inheritAttrs: true,
    props:{
        someData: String
    }
}
</script>
<style scoped>
h1{
    color: red !important;
}
</style>