<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model="username">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容" v-model="connect"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" class="btn btn-default pull-right" @click="addComment">提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "Add",
  props:['addComments'],
  data(){
    return{
      username:'',
      connect:''
    }
  },
  methods:{
    addComment(){
      let {username,connect} = this;
      if (username.trim()&&connect.trim()){
        let id =Date.now();
        let obj = {
          id,
          username,
          connect
        }
        this.addComments(obj);
      }else{
        alert('请输入合法的用户名和内容！')
      }
      this.username=''
      this.connect=''
    }
  }
}
</script>

<style scoped>

</style>