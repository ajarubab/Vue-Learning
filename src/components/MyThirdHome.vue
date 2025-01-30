<template>
    <h1>My Third Home</h1>
    <h2>{{ msgToThirdHome }}</h2>
    <button v-on:click="getThirdHomeMsg(msgToSecongHome)">Send Msg to Second Home</button>
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
    }
}
</script>
<style scoped>
h1 {
    color: black !important;
}
</style>