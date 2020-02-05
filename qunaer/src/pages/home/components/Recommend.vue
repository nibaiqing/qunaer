<template>
  <div class="recommend-container">
    <div class="title">今日推荐</div>
    <ul class="recommend-wrapper">
      <li class="recommend-list border-bottom" v-for="item of recommendList" :key="item.id">
        <img class="recommend-img" :src="item.imgUrl">
        <div class="recommend-about">
          <p class="recommend-title">{{item.title}}</p>
          <p class="recommend-desc">{{item.desc}}</p>
          <p class="recommend-price"><span>¥{{item.price}}</span><span class="recommend-text">起</span>
          </p>
        </div>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'HomeRecommend',
  data () {
    return {
      recommendList: [
        {
          'id': '0001',
          'imgUrl': 'https://imgs.qunarzz.com/vs_ceph_vs_tts/a2ba98f7-a7dc-4b86-be43-2802a1206879.jpg_r_480x320x90_3e4dbe86.jpg',
          'title': '上海-普吉岛 6天跟团游',
          'desc': '泰国普吉岛6天半自由行❀180度海景房&泳池别墅❀双岛双出海',
          'price': '2180'
        },
        {
          'id': '0002',
          'imgUrl': 'https://imgs.qunarzz.com/vs_ceph_vs_tts/af5185d2-e013-43cb-8ef3-5a0a9988844e.jpg_r_480x320x90_d64374ad.jpg',
          'title': '上海-泰国 7天跟团游',
          'desc': '泰国曼谷芭提雅金沙岛7天跟团游|无强消|高档型酒店+餐餐全含',
          'price': '2299'
        },
        {
          'id': '0003',
          'imgUrl': 'https://imgs.qunarzz.com/p/tts9/1805/2f/5b48eb6ac42d0b02.jpg_r_480x320x90_7c156731.jpg',
          'title': '上海-日本 6天跟团游',
          'desc': '春节尾单丨日本本州古都5晚6日丨品质住宿+日式温泉体验+奈良萌鹿+探秘富士山',
          'price': '4223'
        },
        {
          'id': '0004',
          'imgUrl': 'https://imgs.qunarzz.com/p/tts3/1709/41/becd3c7f9ee5a402.jpg_r_390x260x90_6234e2cd.jpg',
          'title': '上海-泰国 6天跟团游',
          'desc': '小资旅程丨普吉岛4晚6日游+国五海景房+步入式泳池别墅+网红餐厅+燕窝下午茶',
          'price': '2080'
        }
      ]
    }
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
