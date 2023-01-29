<template>
  <div class="hello">
   <h1>{{msg}}</h1>
   <h1>{{data.name}}</h1>
   <button @click="plus">点我+1</button>
   <h1>子组件：{{ data.count }}</h1>
  </div>
</template>

<script>
import { reactive } from '@vue/reactivity'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  // 子传父
  setup(props,{emit}) {
    const data = reactive({
      name: '小白',
      count:1
    })
    const plus = () => {
      data.count += 1
      emit('pplus',data.count)
    }
    return {data,plus}
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
