<template>
    <h1>My Fourth Home</h1>
    <h2>Use of Non-Props for Data Passing</h2>
    <h3>{{ someData }}</h3>
    <div v-bind="$attrs">
        <h2>Apple</h2>
        <h2>Mango</h2>
        <h2 v-bind="$attrs">Banana</h2>
        <h2>{{ someData }}</h2>
    </div>
    <h2>------------------------ Use of Computed Block ----------------------------------<br></h2>
    <h3>Principal = {{ P }}</h3>
    <h3>Rate of Interest = {{ R }}</h3>
    <h3>Time = {{ T }}</h3>
    <h3>The SI is : {{ getSI }} Rupees only.</h3>
    <h3>The Total Amout is : {{ getTotalAmount }} Rupees only.</h3>
    <h2>----------------------------------------------------------<br></h2>
</template>
<script>
export default {
    name: "MyFourthHome",
    inheritAttrs: true,
    data() {
        return {
            P: Math.floor(Math.random()*1000),
            R: Math.floor(Math.random()*10),
            T: Math.floor(Math.random()*10),
        }
    },
    props: {
        someData: String
    },
    computed: {
        getSI() {
            let SI = (this.P * this.R * this.T) / 100;
            return SI;
        },
        getTotalAmount() {
            let Total = (this.P+(this.P * this.R * this.T) / 100);
            return Total;
        },
    }
}
</script>
<style scoped>
h1 {
    color: red !important;
}
</style>