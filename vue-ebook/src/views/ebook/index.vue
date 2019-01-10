<template>
    <div class="ebook">
      百度
      <helloWorld msg="hello"></helloWorld>
    </div>
</template>

<script>
  import helloWorld from '../../components/HelloWorld'
    export default {
        name: "index",
        components:{
          helloWorld
        }
    }
</script>

<style lang="scss" scoped>
  @import "../../assets/style/global";

</style>
