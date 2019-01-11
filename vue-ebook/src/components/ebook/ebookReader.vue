<template>
    <div class="ebook">
      <div class="read-wrapper">
        <div id="read"></div>
        <div class="mask">
          <div class="left" @click="prevPage"></div>
          <div class="center"></div>
          <div class="right" @click="nextPage"></div>
        </div>
      </div>
    </div>
</template>

<script>
  import {mapGetters} from 'vuex'
  import  Epub from 'epubjs'
  global.epub = Epub;
  export default {
        computed:{
          ...mapGetters(['fileName'])
        },
        name: "index",
        methods:{
          prevPage(){
            if(this.rendition){
              this.rendition.prev()
            }
          },
          nextPage(){
            if(this.rendition){
              this.rendition.next()
            }
          }
        },
        mounted() {
          //状态管理
          this.$store.dispatch('setFileName',3)

          //动态路由
          console.log(this.$route.params.fileName);

          //阅读
          this.book = new Epub('./练就一双精确识人眼.epub');
          this.rendition = this.book.renderTo('read',{
            width:window.innerWidth,
            height:window.innerHeight,
            method:'default'
          });
          this.rendition.display();
        }
  }
</script>

<style lang="scss" scoped>
  @import "../../assets/style/global";
  .ebook{
    position: relative;
    .read-wrapper{
      .mask{
        position: absolute;
        top: 0;
        left: 0;
        display: flex;
        z-index: 100;
        width: 100%;
        height: 100%;
        .left{
          flex: 0 0 px2rem(100);
        }
        .center{
          flex: 1;
        }
        .right{
          flex: 0 0 px2rem(100);
        }
      }
    }
  }
</style>
