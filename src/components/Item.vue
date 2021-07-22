<template>
  <li @mouseover ="Del=true" @mouseout="Del=false" :class="{ myClass:Del }">
    <label>
      <input type="checkbox" v-model="todo.isOver"/>
      <span>{{todo.connect}}</span>
    </label>
    <button class="btn btn-danger" v-show="Del" @click="delTodo">删除</button>
  </li>
</template>

<script>
export default {
  name: "Item",
  props:{
    todo:Object,
    index:Number,
    delTodos:Function
  },
  data(){
    return{
      Del:false
    }
  },
  methods:{
    delTodo(){
      this.delTodos(this.index);
    }
  }
}
</script>

<style scoped>
/*item*/
.myClass{
  background-color: #EDEDED	;
}

li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}

</style>