<template>
  <div id="app">
    <router-view/>
  </div>
</template>
<script>
  //响应式字体大小
  document.addEventListener('DOMContentLoaded',()=>{
    const html = document.querySelector('html');
    let fontSize = window.innerWidth/10;
    fontSize = fontSize>50 ? 50 : fontSize;
    html.style.fontSize = fontSize + 'px'
  })
</script>
<style lang="scss">
  @import "./assets/style/global.scss";

  #app{
    width: 100%;
    height: 100%;
    overflow: hidden;
  }
</style>
