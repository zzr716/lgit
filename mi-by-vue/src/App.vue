<template>
  <div id="app">
    <top-bar></top-bar>
    <top-header></top-header>
    <top-banner></top-banner>
    <top-sub></top-sub>
    <goods></goods>
    <temp-footer></temp-footer>
    <play-video :play-config="playConfig"></play-video>
  </div>
</template>

<script>
import TopBar from './components/topbar'
import TopHeader from './components/topheader'
import TopBanner from './components/topbanner'
import TopSub from './components/topsub'
import Goods from './components/goods'
import TempFooter from './components/tempfooter'
import PlayVideo from './components/common/playvideo'
export default {
  name: 'app',
  data () {
    return {
      playConfig: {}
    }
  },
  ready () {
    this.recivePlayVideo()
  },
  methods: {
    recivePlayVideo () {
      this.$on('play', function (opts) {
        this.playConfig = opts
      })
    }
  },
  components: {
    'top-bar': TopBar,
    'top-header': TopHeader,
    'top-banner': TopBanner,
    'top-sub': TopSub,
    'goods': Goods,
    'temp-footer': TempFooter,
    'play-video': PlayVideo
  }
}
</script>

<style>
@import './assets/css/base.css';
</style>
