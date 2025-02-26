<template>
    <h1>My Third Home</h1>
    <h2>Msg From Second Home is : {{ msgToThirdHome }}</h2>
    <button v-on:click="getThirdHomeMsg(msgToSecongHome)">Click to Get Msg From 3rd Home to 2nd Home </button>
    <br>
    <!-- <br>
    <button v-on:click="getdata1">Click me to type in Red alphabets</button>
    <br>
    <button v-on:click="getdata2">Click me to type in Blue alphabets</button>
    <br><br>
    <ul>
        <li v-for="item in error" v-bind:key="item">{{ item }} Missing</li>
    </ul>
    <br><br>
    <form>
        <label>Username : </label>
        <input type="text" placeholder="Enter Username" v-model="formDetails.username" />
        <br><br>
        <label>Password : </label>
        <input type="password" placeholder="Enter Password" v-model="formDetails.password" />
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
        <input type="radio" value="male" v-model="formDetails.gender">
        <br>
        <label for="female">Female</label>
        <input type="radio" value="female" v-model="formDetails.gender">
        <br>
        <button type="button" v-on:click="loginData">Sign In</button>
    </form>
    <h1>Form Modifiers</h1>
    <h3>------------------------------------------------</h3>
    <h2>Use of dot trim dot lazy modifier</h2>
    <input type="text" v-model.trim="data1" />
    <h2>Data with trim modifier : {{ data1 }}</h2>
    <h2>Datatype is : {{ typeof(data1) }}</h2>
    <h3>------------------------------------------------</h3>
    <h2>Use of dot trim dot lazy modifier</h2>
    <input type="lazy" v-model.lazy="data2" />
    <h2>Data with lazy modifier : {{ data2 }}</h2>
    <h2>Datatype is : {{ typeof(data2) }}</h2>
    <h3>------------------------------------------------</h3>
    <h2>Use of dot number dot lazy modifier</h2>
    <input type="number" v-model.number.lazy="data3" />
    <h2>Data is number.lazy modifier: {{ data3 }}</h2>
    <h2>Datatype is : {{ typeof(data3) }}</h2>
    <h3>------------------------------------------------</h3> -->
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
            formDetails: {
                username: "",
                password: "",
                country: "",
                technology: [],
                gender: "",
            },
            error: [],
            data1:"",
            data2:"",
            data3:"",
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
        loginData() {
            this.error = [];
            for (const item in this.formDetails) {
                if (this.formDetails[item] === "" || this.formDetails[item].length == 0) {
                    this.error.push(item)
                }
            }
            console.warn("Error data : ", this.error)
            if (this.error.length == 0) {
                console.warn("Login data : ", this.formDetails)
                alert("Data Submitted Successfully.")
            }
        }
    }
}
</script>
<style scoped>
h1 {
    color: black !important;
}
</style>