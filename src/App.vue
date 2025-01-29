<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="App Dot Vue Component"/>
  <MyHome/>
  <!-- <MySecondHome/> -->
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MyHome from './components/MyHome.vue';
// import MySecondHome from './components/MySecondHome.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    MyHome,
    // MySecondHome
  }
}
</script>

