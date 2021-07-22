<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <Item v-for="(item,index) in comments" :comment="item" :index="index" :DelComment="DelComment"></Item>
    </ul>
  </div>
</template>

<script>
import Item from "./Item";
export default {
  name: "List",
  components:{
    Item
  },
  props:['comments','DelComment']
}
</script>

<style scoped>
.reply {
  margin-top: 0px;
}
</style>