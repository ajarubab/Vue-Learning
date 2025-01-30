<template>
  <div class="hello">
    <h2>{{ msg }}</h2>
    <h1>The Helloworld component</h1>
  </div>
  <MyHome :msg="citizen" />
  <MySecondHome :msg="citizen" />
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
  },
  data(){
    return{
      citizen : "Indian"
    }
  }
}
</script>
<style scoped>
h1 {
  color: red;
}
</style>