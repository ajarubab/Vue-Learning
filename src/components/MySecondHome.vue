<template>
    <h1>The Second Home : Child Component</h1>
    <h1>I am an {{ msg }} in Russia.</h1>
    <!-- <h1> Working Above MyThirdHome {{ msgFromThird }}</h1>     -->
    <MyThirdHome msgToThirdHome="Hello from Second Home" :getThirdHomeMsg="getMsgFromThirdHome"/>
    <h1> Msg from Third Home :  {{ msgFromThird }}</h1>    
    <!-- <h1 v-if="isSecondHome">My Second Home</h1>

    <h1 v-if="isRed" style="color: red;">Red Light</h1>
    <h1 v-else style="color: green;">Green Light</h1>
    <button v-on:click="isRed = !isRed">Red/Green</button>

    <ul>
        <li v-for="item in technology" :key="item">
            {{ item }}
        </li>
    </ul>

    <div>
        <h1>{{ jaiKara }}</h1>
        <h2>{{ details }}</h2>
        <h2>{{ details.name }}</h2>
        <button v-on:click="clickFunc">Click to invoke parent function</button>

        <ul>
            <li v-for="item in theData" :key="item.name" class="info">
                <h3>{{ item.name }}</h3>
                <h3>{{ item.email }}</h3>
                <button v-on:click="getMyName(item.name)">Get Name</button><br><br>
                <button v-on:click="getMyName(item.email)">Get Email</button><br><br>
            </li>
        </ul>
    </div>

    <h1 class="otherclass" :class="{ light: isOn }">Light</h1>
    <button v-on:click="isOn = !isOn">ON/OFF</button>

    <h2 :class="multiFavour">class binded favours.</h2>
    <button v-on:click="applyStyles">Lit Me Up</button> -->
<MyFourthHome someData="Some data to 4th Home from 2nd Home" id="raja-babu-001" name="raja"/>
</template>

<script>
import MyFourthHome from './MyFourthHome.vue';
import MyThirdHome from './MyThirdHome.vue';

export default {
    name: 'MySecondHome',
    components: {
        MyThirdHome,
        MyFourthHome
    },
    props: {
        jaiKara: String,
        details: Object,
        clickFunc: Function,
        theData: Array,
        getMyName: Function,
        msg: String,
    },
    data() {
        return {
            isSecondHome: true,
            isRed: false,
            technology: ['Java', 'Php', 'Node', 'Laravel'],
            isOn: true,
            lighten: false,
            isItalic: false,
            bigFont: false,
            msgFromThird: ""
        }
    },
    computed: {
        multiFavour() {
            return {
                isItalic: this.isItalic,
                bigFont: this.bigFont,
                light: this.lighten
            };
        }
    },
    methods: {
        applyStyles() {
            this.lighten = !this.lighten,
                this.isItalic = !this.isItalic,
                this.bigFont = !this.bigFont
        },
        getMsgFromThirdHome(msg)
        {
            alert(msg)
            this.msgFromThird = msg
        }
    }

}
</script>
<style scoped>
h1{
    color: magenta;
}

h2 {
    color: red;
}

.light {
    background-color: red;
    color: yellow;
    width: 200px;
}

.info {
    background-color: lightgoldenrodyellow;
    border-bottom: 2px solid black;
    margin-bottom: 20px;
    padding: 10x;
    width: 200px;
}

.isItalic {
    font-style: italic;
}

.bigFont {
    font-size: 22px;
}
</style>