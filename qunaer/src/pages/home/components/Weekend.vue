<template>
  <div class="recommend-container">
    <div class="title">周末游</div>
    <ul class="recommend-wrapper">
      <li class="recommend-list" v-for="item of list" :key="item.id">
        <div class="img-wrapper">
          <img class="recommend-img" :src="item.imgUrl">
        </div>
        <p class="recommend-title">{{item.title}}</p>
        <p class="recommend-desc">{{item.desc}}</p>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeWeekend',
  props: {
    list: Array
  },
  data () {
    return {}
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
@import '~styles/variable.styl'
.recommend-container
  .title
    color: $backTextColor
    font-size: 0.32rem
    background: #eee
    line-height: .72rem
    text-indent: .2rem
    height: .72rem
  .recommend-wrapper
    width: 100%
    .recommend-list
      padding-bottom: 0.16rem
      .img-wrapper
        width: 100%
        overflow: hidden
        height: 0
        padding-bottom: 38.16%
        margin-bottom: .16rem
        .recommend-img
          display:block
          width: 100%
          height: auto
      .recommend-title
        font-size: .28rem
        line-height: 1.2
        color: $backTextColor
        ellipsis()
        padding-left: .1rem
      .recommend-desc
        font-size: .26rem
        line-height: .44rem
        color: #999
        ellipsis()
        padding-left: .1rem
</style>
