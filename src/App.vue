<template>
  <div>
    <Header></Header>
    <div class="container">
      <Add :addComments="addComments"></Add>
      <List :comments="comments" :delComment="delComment"></List>
    </div>
  </div>
</template>

<script>
import Add from "./components/Add";
import List from "./components/List";
import Header from "./components/Header";
export default {
  name: "App",
  components:{
    Add,
    List,
    Header
  },
  data(){
    return{
      comments:[
        {id:1,username:'小红',connect:'第一'},
        {id:2,username:'小黄',connect:'第二'},
      ]
    }
  },
  methods:{
    addComments(comment) {
      this.comments.unshift(comment);
    },
    delComment(index){
      this.comments.splice(index,1);
    }
  }
}
</script>

<style scoped>

</style>