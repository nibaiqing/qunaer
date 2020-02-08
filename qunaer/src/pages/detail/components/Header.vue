<template>
  <div>
    <router-link
      class="header-circle"
      tag="div"
      to="/"
      v-show="showCircle"
    >
      <div class="iconfont circle-back-icon">&#xe609;</div>
    </router-link>
    <div
      class="header-fixed"
      v-show="!showCircle"
      :style="opacityStyle"
    >
      <router-link to="/">
        <div class="iconfont fixed-back-icon">&#xe609;</div>
      </router-link>
      景点详情
    </div>
  </div>
</template>
<script>
export default {
  name: 'DetailHeader',
  data () {
    return {
      showCircle: true,
      opacityStyle: {
        opacity: 0
      }
    }
  },
  methods: {
    handleScroll () {
      const scrollTop = document.documentElement.scrollTop
      if (scrollTop > 60) {
        let opacity = scrollTop / 140
        opacity = opacity > 1 ? 1 : opacity
        this.opacityStyle = { opacity }
        this.showCircle = false
      } else {
        this.showCircle = true
      }
    }
  },
  activated () {
    window.addEventListener('scroll', this.handleScroll)
  },
  deactivated () {
    window.removeEventListener('scroll', this.handleScroll)
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  .header-circle
    position: absolute
    left: .2rem
    top: .2rem
    width: .8rem
    height: .8rem
    line-height: .8rem
    text-align: center
    border-radius: .4rem
    background: rgba(0, 0, 0, .5)
    .circle-back-icon
      font-size: .6rem
      color: #fff
  .header-fixed
    position: fixed
    z-index: 2
    top: 0
    right: 0
    left: 0
    background: $bgColor
    color: #fff
    font-size: .32rem
    height: $headerHeight
    line-height: $headerHeight
    text-align: center
    .fixed-back-icon
      position: absolute
      left: 0
      bottom: 0
      width: .64rem
      font-size: .4rem
      text-align: center
      color: #fff
      float: left
</style>
