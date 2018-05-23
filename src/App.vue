<template>
  <div id="app">
    <div v-for="(item, index) in audios" :key="index">
      <VueAudio :src="item.url"
                :theControlList="item.controlList"
                displayType="text"
      ></VueAudio>
    </div>

    <div><h3>With More</h3></div>
    <div>
      <p>With Border</p>
      <VueAudio :src="mp3Url"
                border
                theControlList="onlyOnePlaying"></VueAudio>
    </div>
    <div>
      <p>With Custom Color</p>
      <p>color: #66cc22</p>
      <VueAudio :src="mp3Url"
                border
                color="#66cc22"
                theControlList="onlyOnePlaying"></VueAudio>
    </div>
    <div>
      <p>With Icon</p>
      <VueAudio :src="mp3Url"
                border
                color="#66cc22"
                displayType="normal"
                theControlList="onlyOnePlaying"></VueAudio>
    </div>
    <div>
      <p>Loop Play</p>
      <VueAudio :src="mp3Url"
                border
                loop
                color="#66cc22"
                displayType="text"
                theControlList="onlyOnePlaying"></VueAudio>
    </div>
  </div>
</template>

<script>
import VueAudio from './components/VueAudio'

export default {
  name: 'app',
  components: {
    VueAudio
  },
  data () {
    return {
      audios: [
        {
          url: './static/horse.ogg',
          controlList: 'onlyOnePlaying'
        },
        {
          url: './static/horse.ogg',
          controlList: 'noDownload noMuted onlyOnePlaying'
        }, {
          url: './static/horse.ogg',
          controlList: 'noDownload noVolume noMuted onlyOnePlaying'
        }, {
          url: './static/horse.ogg',
          controlList: 'noDownload noSpeed onlyOnePlaying'
        }
      ],
      mp3Url: './static/test.mp3'
    }
  }
}
</script>

<style>

</style>
