<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe609;</div>
    </div>
    <div class="header-input">
      <span class="iconfont search-icon">&#xe604;</span>
      请输入城市/景点/游玩主题
    </div>
    <div class="header-right">
      {{city}}
      <span class="iconfont arrow-icon">&#xe64a;</span>
    </div>
  </div>
</template>
<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  }
}
</script>
<style  scoped lang="stylus">
@import '~styles/variable.styl';
.header
  display: flex
  align-items: center
  background: $bgColor
  color: #fff
  height: .86rem
  .header-left
    width: .64rem
    .back-icon
      font-size: .4rem
      text-align: center
  .header-input
    padding-left: .2rem
    margin-left: .2rem
    height: .62rem
    line-height: .62rem
    flex: 1
    color: #ccc
    background: #fff
    border-radius: .1rem
    .search-icon
      font-size: .30rem
  .header-right
    width: 1.22rem
    text-align: center
    .arrow-icon
      margin-left: -.04rem
      font-size: .24rem
</style>
