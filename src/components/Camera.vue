<template>
  <div class="camera">
    <video ref="video" autoplay class="feed"></video>
    <button class="snap" @click="$emit('takePicture')">SNAP</button>
  </div>
</template>

<script>
export default {
  name: 'camera',
  beforeMount(){
    this.init();
  },
  methods:{
    init(){
      if('mediaDevices' in navigator && 'getUserMedia' in navigator.mediaDevices){
          let constraints = {
            video: {
              width: {
                min: 640,
                ideal: 1280,
                max: 1920
              },
              height: {
                min: 360,
                ideal: 720,
                max: 1080
              }
            }
          };
        navigator.mediaDevices.getUserMedia({video:true}).then(stream => {
          const videoPlayer = this.$refs.video;
          videoPlayer.srcObject = stream;
          videoPlayer.play();

        })
      }else{
        alert("Cannot get media devices")
      }
    },
  }

}
</script>

<style scoped lang="scss">
.camera{
  display: block;
  margin: 0 auto;
  width: 50vw;
  height: 50vh;
  padding: 25px;
  box-sizing: border-box;
  .feed{
    display: block;
    width: 100%;
    max-width: 1280px;
    margin: 0 auto;
    background-color: #171717;
    box-shadow: 6px 6px 12px 0px rgba(0, 0, 0, 0.25);
  }

  .snap{
    display: block;
    width: 75px;
    height: 75px;
    border-radius: 50%;
    margin: 25px auto;
    background-color: transparentize($color: #FFCE00, $amount: .5);
    border: 1px solid #171717;
    outline: none;
    cursor: pointer;

    &:hover{
      background-color: #FFCE00;

    }
    &:active{
      background-color: darken($color: #FFCE00, $amount: 10)
    }

  }
  
}
</style>
