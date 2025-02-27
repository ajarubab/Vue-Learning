<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <!-- <h1>App.vue component : The Root Vue Component</h1> -->
  <!-- <HelloWorld msg="msg to helloworld.vue from app.vue using props"/> -->
  <!-- <MyHome/> -->
  <!-- <MySecondHome/> -->

  <!-- <h1>Using the components dianamically</h1>
  <button @click="tab = 'HelloWorld'">Show HelloWorld Component content</button><br>
  <button @click="tab = 'MyHome'">Show MyHome Component content</button><br>
  <button @click="tab = 'MySecondHome'">Show MySecondHome Component content</button><br>
  <button @click="tab = 'MyThirdHome'">Show MyThirdHome Component content</button><br>
  <button @click="tab = 'MyFourthHome'">Show MyFourthHome Component content</button><br>
  <component :is="tab" /> -->
  <button v-on:click="show = !show">Toggle</button>
  <Footer v-if="show" />

</template>

<script>
import Footer from './components/footer.vue';

// import HelloWorld from './components/HelloWorld.vue'
// import MyHome from './components/MyHome.vue';
// import MySecondHome from './components/MySecondHome.vue';
// import MyThirdHome from './components/MyThirdHome.vue';
// import MyFourthHome from './components/MyFourthHome.vue';

export default {
  name: 'App',
  components: {
    // HelloWorld,
    // MyHome,
    // MySecondHome,
    // MyThirdHome,
    // MyFourthHome,
    Footer
  },
  data() {
    return {
      tab: '',
      show: true
    }
  }
}
</script>
