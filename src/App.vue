<template>
  <div id="app">
    <Camera @takePicture="takePicture"/>
    <Gallary/>
  </div>
</template>

<script>
import Camera from './components/Camera.vue'
import Gallary from './components/Gallary.vue'

export default {
  name: 'app',
  components: {
    Camera,
    Gallary
  },
  methods:{
    takePicture(){
      let ratio = (window.innerHeight > window.innerWidth) ? 16 / 9 : 9 / 16 ;
      const picture = document.querySelector("canvas");
      const ctx = picture.getContext("2d");
      ctx.imageSmoothingEnabled = true;
      ctx.imageSmoothingQuality = "high";
      ctx.drawImage(document.querySelector("video"), 0, 0, picture.width, picture.height);
    }
  }
}
</script>

<style lang="scss">
body{
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0px;
  background-color: #F3F3F3;
}
</style>
