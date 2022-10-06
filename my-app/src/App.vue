<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <input :value="inputValue" />
    <button @click="pushArr">添加</button>
    <!-- <ul>
      <todo-item v-for="(item, index) in arr" :index="index" :item="item"  :key="index">
        {{item}}
      </todo-item>
    </ul> -->
    <ul>
      <todo-item v-for="(item, index) in arr" :index="index" :key="index">
        <template v-slot:ant-error="childProps">
          <span :style="{color: childProps.checked ? 'red' : 'blue'}" >{{item}}</span>
        </template>
      </todo-item>
    </ul>
    <EventItem></EventItem>
    <!-- 双向绑定 -->
    <personInfo></personInfo>
  </div>
</template>

<script>
import TodoItem from './components/todoItem.vue'
import EventItem from './components/eventTest.vue'
import personInfo from './views/1-1/index.vue'

export default {
  name: 'App',
  data() {
    return {
      msg: 'hello word',
      inputValue: 1,
      arr: ['吃饭', '睡觉', '打豆豆']
    }
  },
  methods: {
    pushArr() {
      this.inputValue++;
      this.arr.push(this.inputValue);
    }
  },
  components: {
    TodoItem,
    EventItem,
    personInfo
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
