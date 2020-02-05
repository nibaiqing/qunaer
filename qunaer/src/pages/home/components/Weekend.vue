<template>
  <div class="recommend-container">
    <div class="title">周末游</div>
    <ul class="recommend-wrapper">
      <li class="recommend-list" v-for="item of recommendList" :key="item.id">
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
  data () {
    return {
      recommendList: [
        {
          'id': '0001',
          'imgUrl': 'http://imgs.qunarzz.com/vc/6d/9f/35/b8ad5468f73fd60ec0ced086f6.jpg_92.jpg',
          'title': '上海-普吉岛 6天跟团游',
          'desc': '泰国普吉岛6天半自由行❀180度海景房&泳池别墅❀双岛双出海',
          'price': '2180'
        },
        {
          'id': '0002',
          'imgUrl': 'http://imgs.qunarzz.com/vc/24/36/10/3fc94d042ae62de380581d4c98.jpg_92.jpg',
          'title': '上海-泰国 7天跟团游',
          'desc': '泰国曼谷芭提雅金沙岛7天跟团游|无强消|高档型酒店+餐餐全含',
          'price': '2299'
        },
        {
          'id': '0003',
          'imgUrl': 'http://imgs.qunarzz.com/vc/ad/7c/fe/037d1a400372ff57b0030d1d1c.jpg_92.jpg',
          'title': '上海-日本 6天跟团游',
          'desc': '春节尾单丨日本本州古都5晚6日丨品质住宿+日式温泉体验+奈良萌鹿+探秘富士山',
          'price': '4223'
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
    .recommend-list
      padding-bottom: 0.16rem
      .img-wrapper
        width: 100%
        overflow: hidden
        height: 0
        padding-bottom: 30.47%
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
