<template>
    <h1>My Third Home</h1>
    <h2>{{ msgToThirdHome }}</h2>
    <button v-on:click="getThirdHomeMsg(msgToSecongHome)">Send Msg to Second Home</button>
    <br><br>
    <input type="text" ref="nameInput" />
    <br>
    <button v-on:click="getdata1">Click me to type in Red alphabets</button>
    <br>
    <button v-on:click="getdata2">Click me to type in Blue alphabets</button>
    <br><br>
    {{ this.formDetails }}
    <br><br>
    <form>
        <label>Username : </label>
        <input type="text" placeholder="Enter Username" v-model="formDetails.username"/>
        <br><br>
        <label>Password : </label>
        <input type="password" placeholder="Enter Password" v-model="formDetails.password"/>
        <br><br>

        <label>Country : </label>
        <select v-model="formDetails.country">
            <option value="India">India</option>
            <option value="China">China</option>
            <option value="USA">USA</option>
            <option value="Russia">Russia</option>
        </select>
        <br><br>
        <label>Technology : </label><br>
        <label for="java">Java</label>
        <input type="checkbox" value="java" id="java" v-model="formDetails.technology">
        <br>
        <label for="php">PHP</label>
        <input type="checkbox" value="php" id="php" v-model="formDetails.technology">
        <br>
        <label for="node">Node</label>
        <input type="checkbox" value="node" id="node" v-model="formDetails.technology">
        <br><br>

        <label for="male">Male</label>
        <input type="radio"  value="male" v-model="formDetails.gender">
        <br>
        <label for="female">Female</label>
        <input type="radio"  value="female"  v-model="formDetails.gender">
        <br>
        <button type="button" v-on:click="loginData">Sign In</button>
    </form>
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
            msgToSecongHome: "Hello from Third Home",
            formDetails:{
                username : "",
                password : "",
                country : "",
                technology : [],
                gender : "",
            }
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
        },
        loginData(){
            console.warn("Login data : ", this.formDetails)
        }
    }
}
</script>
<style scoped>
h1 {
    color: black !important;
}
</style>