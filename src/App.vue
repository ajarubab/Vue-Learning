<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <h1>App.vue component : The Root Vue Component</h1>
  <HelloWorld msg="msg to helloworld.vue from app.vue using props"/>
  <!-- <MyHome/> -->
  <!-- <MySecondHome/> -->
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// import MyHome from './components/MyHome.vue';
// import MySecondHome from './components/MySecondHome.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    // MyHome,
    // MySecondHome
  }
}
</script>

