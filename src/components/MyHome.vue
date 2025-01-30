<template>

    <h1>My Home Component : The Parent Home</h1>
    <h1>I am an {{ msg }} in USA.</h1>
    <!-- <h2>{{ count }}</h2>
    <input type="number" v-model="count" />
    <button v-on:click="incCount()">increase</button>
    <button v-on:click="decCount()">decrease</button>
    <h1>4 power raised by 2 is = {{ 4 ** 2 }}</h1>
    <h1>The length of word 'ram' is : {{ 'ram'.length }}</h1>
    <h1>My Name : {{ getName() }}</h1>
    <h1>{{ getAge(24) }}</h1>
    <h1>My Email : {{ email }}</h1>
    <h1>My Country : {{ country = 'India' }}</h1>
    <h1>My All Data : {{ getData() }}</h1>
    <h1>My partial Data 1: {{ getData().name }}</h1>
    <h1>My partial Data 2: {{ getData().area }}</h1>
    <h1>My partial Data 3: {{ getData().email }}</h1>
    <button v-on:click="clickEvent1()"> Button 1</button><br><br>
    <button v-on:click="clickEvent2('Button 2 clicked')"> Button 2</button><br><br>
    <button v-on:dblclick="clickEvent2('Button Double clicked')"> Double click here</button><br><br>
    <input type="text" placeholder="Enter username" v-model="username" /><br><br>
    <input type="password" placeholder="Enter password" v-model="password" /><br><br>
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
    <input type="radio" value="student" name="who" id="student" v-model="who">
    <label for="developer">Developer</label>
    <input type="radio" value="developer" name="who" id="developer" v-model="who">
    <h2>I am a {{ who }}</h2> -->



    <!-- <MySecondHome 
        jaiKara="Jai Shree Ram" 
        :details="userDetails[0]" 
        :clickFunc="clickEvent1" 
        :theData="myData"
        :getMyName="getTheName"
    />

    <div v-html="tag"></div> -->
</template>

<script>
// import MySecondHome from './MySecondHome.vue';
export default {
    name: 'MyHome',
    props:{
        msg:String
    },
    components: {
        // MySecondHome
    },
    data() {
        return {
            email: "imraja@bharat.in",
            country: '',
            count: 10,
            username: null,
            password: null,
            technologies: [],
            who: null,
            userDetails: [
                {
                    name: "Radhe Radhe",
                    Age: 18,
                    country: "India"
                }
            ],
            myData: [
                { name: "raja", email: "raja@abc.com" },
                { name: "ram", email: "ram@abc.com" },
                { name: "raju", email: "raju@abc.com" },
                { name: "raj", email: "raj@abc.com" },
                { name: "rajat", email: "rajat@abc.com" },
                { name: "rajan", email: "rajan@abc.com" },
            ],
            tag: "<h1>This is H1 Tag.</h1>"
        }
    },
    methods: {
        getTheName(a) {
            alert(a);
        },
        getName() {
            return "Raja kumar prasad";
        },
        getAge(num) {
            return `My age is : ${num}`;
        },
        getData() {
            return {
                name: "Ram",
                area: "Ayodhya",
                email: this.email
            }
        },
        getMyIdPass() {
            console.warn("Id password are ", this.username, this.password)
        },
        clickEvent1() {
            alert("Button 1 clicked");
        },
        clickEvent2(data) {
            alert(data);
        },
        incCount() {
            this.count = this.count + 1;
        },
        decCount() {
            this.count = this.count - 1;
        }
    }
}
</script>

<style scoped>
h1 {
    color: blue;
}

h3 {
    color: green;
}
</style>