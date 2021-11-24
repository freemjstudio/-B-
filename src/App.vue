<template>
  <div id="app">
    <div class="jb-box">
      <div class="main">
        <List v-bind:propsdata="todoItems"></List>
      </div>
        <video muted autoplay loop>
        <source src="videos/Network.mp4" type="video/mp4">
        </video>
       <Input v-on:addTodo="addTodo"></Input>
      </div>
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
  body { padding: 0px;
        margin: 0px;
        text-align: center;
        overflow: hidden;
        background-color: #F6F6F8;
        vertical-align: center;
     }

  .jb-box {
    weight: 100%;
    margin: 0px auto;
    position: relative;
  }

  video { width: 100%; }
  .main {
    position: absolute;
  }

  input {
    border-style: groove;
    width: 200px;
  }
  .shadow {
    box-shadow: 5px 10px 10px rgba(0, 0, 0, 0.03)
  }
</style>
