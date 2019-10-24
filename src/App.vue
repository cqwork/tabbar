<template>
  <div id="app">
    <router-view></router-view>
    <MainTab/>
  </div>
</template>

<script>
  import MainTab from 'components/MainTab'
  export default {
    name: 'App',
    components:{
      MainTab
    }
  }
</script>

<style>
  @import './assets/css/base.css';

</style>
