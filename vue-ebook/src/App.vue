<template>
  <div id="app">
    <div class="icon iconfont icon-dianzan"></div>
    <span class="text">百度网盘123</span>
    <router-view/>
  </div>
</template>
<script>
  import {mapGetters} from 'vuex'

  export default {
    computed:{
      ...mapGetters(['test'])
    },
    mounted() {
      this.$store.dispatch('setTest',9).then(()=>{
        console.log(this.test)
      })
    }
  }
</script>
<style lang="scss">
  @import "./assets/style/global.scss";
  .text{
    font-size: px2rem(22);
    color: red;
  }
</style>
