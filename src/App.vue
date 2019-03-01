<template>
  <div id="app">
    <Camera @takePicture="takePicture"/>
  </div>
</template>

<script>
import Camera from './components/Camera.vue'

export default {
  name: 'app',
  components: {
    Camera
  },
  methods:{
    takePicture(){
      
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
