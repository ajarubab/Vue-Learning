<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to New Vue tutorial"/>
  <MyHome/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import MyHome from './components/MyHome.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    MyHome
  }
}
</script>

