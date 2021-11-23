<template>
  <div id="app">
    <Header></Header>
    <List v-bind:propsdata="todoItems"></List>
    <Input v-on:addTodo="addTodo"></Input>
    <Footer></Footer>
  </div>
</template>
<script>
import Header from './components/Header.vue'
import List from './components/List.vue'
import Input from './components/Input.vue'
import Footer from './components/Footer.vue'

export default {
  data() {
    return {
      todoItems: []
    }
  },
  methods: {
    clearAll() {
      localStorage.clear();
      this.todoItems = [];
    },
    addTodo(todoItem) {
      // DB에 추가하는 로직
      localStorage.setItem(todoItem, todoItem);
      this.todoItems.push(todoItem);
    }
  },
    create() {
      if (localStorage.length > 0) {
        for (var i = 0; i < localStorage.length; i++) {
          this.todoItmes.push(localStorage.key(i))
        }
      }
    },
  components: {
    'Header': Header,
    'Input': Input,
    'List':List,
    'Footer':Footer
  }
}
</script>

<style>
body {
    text-align: center;
    background-color: #F6F6F8;
  }
  input {
    border-style: groove;
    width: 200px;
  }
  .shadow {
    box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03)
  }
</style>
