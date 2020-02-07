<template>
  <div class="header">
    <div class="header-left">
      <div class="iconfont back-icon">&#xe609;</div>
    </div>
    <div class="header-input">
      <span class="iconfont search-icon">&#xe604;</span>
      请输入城市/景点/游玩主题
    </div>
    <router-link to="/city">
      <div class="header-right">
        {{this.currentCity}}
        <span class="iconfont arrow-icon">&#xe64a;</span>
      </div>
    </router-link>
  </div>
</template>
<script>
import { mapState } from 'vuex'
export default {
  name: 'HomeHeader',
  computed: {
    ...mapState({
      currentCity: 'city'
    })
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
  height: $headerHeight
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
    min-width: 1.02rem
    padding: 0 .1rem
    text-align: center
    color: #fff
    .arrow-icon
      margin-left: -.04rem
      font-size: .24rem
</style>
