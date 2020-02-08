<template>
  <div>
    <div class="banner" @click="handelBannerClick">
      <img class="banner-img" :src="bannerImg" >
      <div class="header-info">
        <p class="banner-title">{{sightName}}</p>
        <p class="banner-number iconfont">&#xe674; {{gallaryImgs.length}}</p>
      </div>
    </div>
    <fade-animation>
      <common-gallery v-show="showGallery" :imgs="gallaryImgs" @close="handelGallerClose"></common-gallery>
    </fade-animation>
  </div>
</template>
<script>
import CommonGallery from 'common/gallery/Gallery'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  components: {
    CommonGallery,
    FadeAnimation
  },
  props: {
    sightName: String,
    bannerImg: String,
    gallaryImgs: Array
  },
  data () {
    return {
      showGallery: false
    }
  },
  methods: {
    handelBannerClick () {
      this.showGallery = true
    },
    handelGallerClose () {
      this.showGallery = false
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl'
  .banner
      overflow: hidden
      height: 0
      padding-bottom: 55%
      position: relative
    .banner-img
      width: 100%
    .header-info
      width: 100%
      position: absolute
      left: 0
      bottom: 0
      line-height: .62rem
      color: #ffffff
      background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, .8))
      .banner-title
        float: left
        font-size: .28rem
        padding: 0 .2rem
      .banner-number
        float: right
        font-size: .24rem
        height: .32rem
        line-height: .32rem
        border-radius: .2rem
        padding: 0 .3rem
        margin-top: .15rem
</style>
