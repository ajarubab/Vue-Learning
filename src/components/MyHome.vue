<template>
    <h2>{{ count }}</h2>
    <input type="number" v-model="count"/>
    <button v-on:click="incCount()">increase</button>
    <button v-on:click="decCount()">decrease</button>
    <h1>My Home Component</h1>
    <h1>2 + 2 = {{ 2 + 2 }}</h1>
    <h1>The length of word 'ram' is : {{ 'ram'.length }}</h1>
    <h1>My Name : {{ getName() }}</h1>
    <h1>{{ getAge(24) }}</h1>
    <h1>My Email : {{ email }}</h1>
    <h1>My Country : {{ country = 'India' }}</h1>
    <h1>My All Data : {{getData() }}</h1>
    <h1>My partial Data 1: {{ getData().name }}</h1>
    <h1>My partial Data 2: {{ getData().area }}</h1>
    <h1>My partial Data 3: {{ getData().email }}</h1>
    <button v-on:click="clickEvent1()"> Button 1</button><br><br>
    <button v-on:click="clickEvent2('Button 2 clicked')"> Button 2</button><br><br>
    <button v-on:dblclick="clickEvent2('Button Double clicked')"> Double click here</button><br><br>
    <input type="text" placeholder="Enter username" v-model="username"/><br><br>
    <input type="password" placeholder="Enter password" v-model="password"/><br><br>
    <button type="button" v-on:click="getMyIdPass()">Submit</button>
    <br><br>
    <label for="php">Php</label>
    <input type="checkbox" value="Php" id="php" v-model="technologies"><br>
    <label for="java">Java</label>
    <input type="checkbox" value="Java" id="java" v-model="technologies"><br>
    <label for="node">Node</label>
    <input type="checkbox" value="Node" id="node" v-model="technologies"><br>
    <h2>Selected values are : {{ technologies }}</h2>
    <br><br>
    <label for="student">Student</label>
    <input type="radio" value="student" name = "who" id="student" v-model="who" >
    <label for="developer">Developer</label>
    <input type="radio" value="developer" name="who" id="developer" v-model="who">
    <h2>I am a {{ who }}</h2>


</template>

<script>
export default {
    name: 'MyHome',
    data() {
        return {
            email: "imraja@bharat.in",
            country: '',
            count: 0,
            username: null,
            password: null,
            technologies: [],
            who: null,
        }
    },
    methods: {
        getName() {
            return "Raja kumar prasad";
        },
        getAge(num) {
            return `My age is : ${num}`;
        },
        getData(){
            return{
                name: "Ram",
                area: "Ayodhya",
                email : this.email
            }
        },
        getMyIdPass(){
            console.warn("Id password are ", this.username, this.password)
        },
        clickEvent1(){
            alert("Button 1 clicked");
        },
        clickEvent2(data){
            alert(data);
        },
        incCount(){
            this.count = this.count+1;
        },
        decCount(){
            this.count =  this.count-1;
        }
    }
}
</script>

<style scoped>
h1 {
    color: blue;
}
</style>