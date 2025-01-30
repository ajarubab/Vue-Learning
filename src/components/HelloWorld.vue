<template>
  <div class="hello">
    <h2>{{ msg }}</h2>
    <h1>The Helloworld component</h1>
  </div>
  <MyHome msg="msg to MyHome.vue from Helloworld.vue using props" />
  <MySecondHome msg="msg to MySecondHome.vue from Helloworld.vue using props" />
</template>

<script>
import MyHome from './MyHome.vue';
import MySecondHome from './MySecondHome.vue';

export default {
  name: 'HelloWorld',
  components: {
    MyHome,
    MySecondHome
  },
  props: {
    msg: String
  }
}
</script>
<style scoped>
h1 {
  color: red;
}
</style>