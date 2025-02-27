<template>
    <h1>My Fourth Home</h1>
    <!-- <h2>Use of Non-Props for Data Passing</h2>
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
    <h2>----------------------- Use of Watcher -----------------------------------<br></h2>
    <h1>Body Temperature : {{ BT.toFixed(1) }}</h1>
    <button v-on:click="BT = BT + 0.5"> + </button>
    <br>
    <button v-on:click="BT= BT - 0.5" > - </button> -->
    <!-- <h2>------------------------ Use of slots ----------------------------------<br></h2>
    <slot>Default Message<h1> when nothing is passes on component calling</h1></slot> -->
    <!-- <div class="cart">
        <upari>
            <slot name="header"></slot>
        </upari>
        <beechWala>
            <slot name="content"></slot>
        </beechWala>
        <neechla>
            <slot name="footer"><button>Get It</button></slot>
        </neechla>
    </div> -->
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
            BT : 98.6,
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
    },
    watch: {
        BT(cur, prev){
            if(cur > 101 && cur < 103 && cur > prev){
                alert ("High Fever, Apply cold-wet cloth on forehead.")
            }
            else if(cur > 103 && cur > prev){
                alert ("Critical Fever Temperature, Get Hospitalised ASAP")
            }
            else if(cur < 96.8 && prev > cur){
                alert ("Body Temperature Dropping, Get Hospitalised ASAP")
            }
        }
    }
}
</script>
<style scoped>
h1 {
    color: red !important;
}
/* button{
    width: 50px;
    height: 30px;
    border: solid 1px;
    font-size: 25px;
    font-weight: bolder;
    background-color: chartreuse;
} */
.cart{
    border: 1px solid;
    padding: 20px;
    margin: 10px;
    text-align: center;
    width: 100px;
    background-color: lightcyan;
}
</style>