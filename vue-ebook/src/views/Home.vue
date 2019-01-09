<template>
  <div class="home">
    <div id="read"></div>
  </div>
</template>

<script>
// @ is an alias to /src
import Epub from 'epubjs'
global.ePub = Epub
export default {
  name: 'home',
  data(){
    return {
      book:''
    }
  },
  mounted() {
    this.book = new Epub('/练就一双精确识人眼.epub');
    this.book.renderTo('read').display()
  }
}
</script>
