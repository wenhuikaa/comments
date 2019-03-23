<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style="display: none">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
        <!-- 有多条评论，所以v-for
        comment交给Item组件 -->
        <Item v-for="(comment,index) in comments" :key="index" :comment="comment"
        :deleteComment="deleteComment" :index="index"/>
    </ul>
  </div>
</template>

<script>
import Item from "./Item.vue"
export default {
  //声明接收属性:这个属性将会成为组件对象的属性，在组件对象里也可以声明data
  props: ["comments","deleteComment"],   //只指定了属性名
  // data(){
  //     return {
  //         a:1
  //     }
  // }
  components:{
      Item
  }
};
</script>

<style>
.reply {
  margin-top: 0px;
}
</style>