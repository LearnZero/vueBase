<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <Header @addTodos="addTodos"></Header>
      <Main :todos="todos" :delTodos="delTodos"></Main>
      <Footer :todos="todos" :updateTodos="updateTodos" @deleteAll="deleteAll"></Footer>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header";
import Main from "./components/Main";
import Footer from "./components/Footer";
export default {
  name: "App",
  data(){
    return{
        todos:JSON.parse(localStorage.getItem('TODO_KEY'))||[]
    }
  },
  watch:{
    todos:{
      deep:true,
      handler(newVal,oldVal){
        localStorage.setItem('TODO_KEY',JSON.stringify(newVal))
      }
    }
  },
  methods:{
    addTodos(todo) {
      this.todos.unshift(todo);
    },
    delTodos(index) {
      this.todos.splice(index,1);
    },
    updateTodos(val){
      this.todos.forEach(item=>item.isOver=val)
    },
    deleteAll(){
      this.todos = this.todos.filter(item=>!item.isOver)
    }
  },
  components:{
    Header,
    Main,
    Footer
  }
}
</script>

<style scoped>
/*app*/
.todo-container {
  width: 600px;
  margin: 0 auto;
}
.todo-container .todo-wrap {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
}
</style>