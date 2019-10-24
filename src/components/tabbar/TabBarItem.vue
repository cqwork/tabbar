<template>
  <div class="tab-bar-item" @click="tabClick">
    <div v-if="!isActive"><slot name="item-img"></slot></div>
      <div v-else><slot name="item-img-active"></slot></div>
    <div
      :style="activeStyle"
    ><slot name="item-text"></slot></div>
  </div>
</template>

<script>
    export default {
      name: "TabBarItem",
      data(){
        return {
          // isShow: true
        }
      },
      computed:{
        isActive(){
          return this.$route.path.indexOf(this.path) === 0
          // console.log(this.$route.path.indexOf(this.path));
        },
        activeStyle(){
          return this.isActive ? {color:this.activeColor}:{}
        }
      },
      props:{
        path: String,
        activeColor: {
          default: 'red',
          type: String
        }
      },
      methods:{
        tabClick(){
          this.$router.push(this.path);
        }
      }

    }
</script>

<style scoped>
  .tab-bar-item{
    flex: 1;
    text-align: center;
    height: 49px;
    font-size: 14px;
  }
  .tab-bar-item img{
    margin-top: 4px;
    width: 24px;
    height: 24px;
    vertical-align: middle;
  }
</style>
