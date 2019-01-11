<template>
  <ebook-reader></ebook-reader>
</template>

<script>
  import ebookReader from "../../components/ebook/ebookReader";
    export default {
      name: "index",
      components:{
          ebookReader
      }
    }
</script>

<style lang="scss" scoped>
  @import "../../assets/style/global";
</style>
