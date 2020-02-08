<template>
  <div class="recommend-container">
    <div class="title">今日推荐</div>
    <ul class="recommend-wrapper">
      <router-link
        tag="li"
        class="recommend-list
        border-bottom"
        v-for="item of list"
        :key="item.id"
        :to="'/detail/' + item.id"
      >
        <img class="recommend-img" :src="item.imgUrl">
        <div class="recommend-about">
          <p class="recommend-title">{{item.title}}</p>
          <p class="recommend-desc">{{item.desc}}</p>
          <p class="recommend-price"><span>¥{{item.price}}</span><span class="recommend-text">起</span>
          </p>
        </div>
      </router-link>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
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
  margin-top: .1rem
  .title
    color: $backTextColor
    font-size: 0.32rem
    background: #eee
    line-height: .72rem
    text-indent: .2rem
    height: .72rem
  .recommend-wrapper
    width: 100%
    overflow: hidden
    padding: .1rem
    .recommend-list
      display: flex
      padding: .02rem 0
      .recommend-img
        width: 1.7rem
        height: 1.7rem
        padding: .1rem
        border-radius: .16rem
      .recommend-about
        position: relative
        flex: 1
        min-width: 0
        padding: .1rem
        .recommend-title
          font-size: .28rem
          line-height: 1.2
          margin-bottom: .04rem
          color: $backTextColor
          ellipsis()
        .recommend-desc
          font-size: .26rem
          line-height: .44rem
          color: #555
          ellipsis()
        .recommend-price
          display: flex
          font-size: .36rem
          position: absolute
          bottom: .05rem
          font-weight: 700
          height: .44rem
          line-height: .44rem
          color: #ff7400
          .recommend-text
            padding-left: .04rem
            font-weight: 100
            font-size: .28rem
</style>
