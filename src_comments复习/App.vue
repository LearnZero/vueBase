<template>
  <div>
    <Header></Header>
    <div class="container">
<!--      <Add :AddComment="AddComment"></Add>-->
<!--      自定义事件复杂写法-->
<!--      <Add ref="add"></Add>-->
<!--      自定义事件事件简单写法-->
      <Add @AddComment="AddComment"></Add>
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
  },
  mounted() {
    // 自定义事件复杂写法
    // this.$refs.add.$on('AddComment',this.AddComment);
  }
}
</script>

<style scoped>

</style>