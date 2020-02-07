<template>
  <div class="header" ref="header">
    <router-link to="/">
      <div class="iconfont back-icon">&#xe609;</div>
    </router-link>
    城市选择
  </div>
</template>
<script>
export default {
  name: 'CityHeader',
  mounted () {
    this.$emit('change', this.$refs.header.offsetHeight)
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl';
.header
  overflow: hidden
  background: $bgColor
  color: #fff
  font-size: .32rem
  height: $headerHeight
  line-height: $headerHeight
  text-align: center
  position: relative
  .back-icon
    position: absolute
    left: 0
    bottom: 0
    width: .64rem
    font-size: .4rem
    text-align: center
    color: #fff
    float: left
</style>
