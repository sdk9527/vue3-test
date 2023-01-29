<template>
  <HelloWorld msg="欢迎来到VUE3" @pplus="plus"/>
  <h1>父组件：{{ data.count }}</h1>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { reactive, ref } from 'vue'
export default {
  name: 'App',
  components: {
    HelloWorld
  },
  setup() {
    const data = ref({count:1})
    const plus = (count) => {
      console.log(count)
      data.value.count = count
    }


    return { data,plus }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
