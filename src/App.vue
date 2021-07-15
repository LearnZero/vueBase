<template>
  <div>
    <Header></Header>
    <div class="container">
      <Add :AddComment="AddComment"></Add>
      <List :comments="comments" :DelComment="DelComment"></List>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header";
import Add from "./components/Add";
import List from "./components/List";
export default {
  name: "App",
  components:{
    Header,
    Add,
    List
  },
  data(){
    return{
      comments:[
        {
          id:1,
          username:'小红',
          connect:'熟练使用prop'
        },
        {
          id:2,
          username:'小黄',
          connect:'熟练使用prop'
        },
      ]
    }
  },
  methods:{
    AddComment(obj){
      this.comments.unshift(obj);
    },
    DelComment(index){
      this.comments.splice(index,1)
    }
  }
}
</script>

<style scoped>

</style>