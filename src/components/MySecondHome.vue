<template>
    <h1>The Second Home : Child Component</h1>

    <h1 v-if="isSecondHome">My Second Home</h1>

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
</template>

<script>
export default {
    name: 'MySecondHome',
    props: {
        jaiKara: String,
        details: Object,
        clickFunc: Function,
        theData: Array,
        getMyName: Function,
    },
    data() {
        return {
            isSecondHome: true,
            isRed: false,
            technology: ['Java', 'Php', 'Node', 'Laravel'],
        }
    }

}
</script>
<style scoped>
h1 {
    color: magenta;
}

h2 {
    color: red;
}

.info {
    background-color: lightgoldenrodyellow;
    border-bottom: 2px solid black;
    margin-bottom: 20px;
    padding: 10x;
}
</style>