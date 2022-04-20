<template>
  <div>
    <audio
      src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3"
      ref="foo"
      controls="true"
    ></audio>
  </div>
</template>

<script>
import AudioVisual from 'vue-audio-visual'
export default {
  name: 'ListenAudio',
  components: {
    AudioVisual
  },
  props: {
    msg: String
  },
  data () {
    return {
      done: false
    }
  },
  created () {
    var player = document.querySelector('#player')
    console.log('player', player)
    try {
      var handleSuccess = function (stream) {
        if (window.URL) {
          player.srcObject = stream
        } else {
          player.src = stream
        }
        console.log('done2')
      }
    } catch (e) {
      console.error(e)
    }
    navigator.mediaDevices
      .getUserMedia({ audio: true, video: false })
      .then(handleSuccess)
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
audio{
    width: 100%;
}
</style>
