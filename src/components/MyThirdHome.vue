<template>
    <h1>My Third Home</h1>
    <h2>{{ msgToThirdHome }}</h2>
    <button v-on:click="getThirdHomeMsg(msgToSecongHome)">Send Msg to Second Home</button>
    <input type="text" ref="nameInput" />
    <button v-on:click="getdata1">Click me to type in Red alphabets</button>
    <button v-on:click="getdata2">Click me to type in Blue alphabets</button>
</template>
<script>
export default {
    name: "MyThirdHome",
    props: {
        msgToThirdHome: String,
        getThirdHomeMsg: Function
    },
    data() {
        return {
            msgToSecongHome: "Hello from Third Home"
        }
    },
    methods: {
        getdata1() {
            this.$refs.nameInput.focus();
            let val = this.$refs.nameInput.value;
            console.warn(val);
            this.$refs.nameInput.style.color = "red"
        },
        getdata2() {
            this.$refs.nameInput.focus();
            let val = this.$refs.nameInput.value;
            console.warn(val);
            this.$refs.nameInput.style.color = "Blue"
        }
    }
}
</script>
<style scoped>
h1 {
    color: black !important;
}
</style>