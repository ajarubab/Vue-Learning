<template>
    <div class="footer">
        <h1 ref="count">{{ count }}. {{greet}}, This is Footer</h1>
        <button v-on:click="count = count +1">Add</button>
    </div>
</template>
<script>
export default {
    name: "FooterComponent",
    unmounted(){
        console.log("unMount finished",this.$refs['count']);
    },
    updated(){
        console.log("updation finished",this.$refs['count'].textContent);
    },
    mounted(){
        console.log("mounted finished",this.$el);
    },
    created(){
        console.log("creation finished");
    },
    data(){
        console.log("into data");
        return {
            greet : "Hello",
            count : 0,
        }
    },
    beforeUnmount() {
        console.log("before unMount",this.$refs['count']);
    },
    beforeUpdate() {
        console.log("before update",this.$refs['count'].textContent);
    },
    beforeCreate() {
        console.log("before created");
    },
    beforeMount() {
        console.log("before Mount",this.$el);
    },
}
</script>
<style>
.footer {
    background-color: beige;
    width: 90%;
    padding: 10%;
    left: 0;
    position: relative;
    bottom: 0;
}
</style>