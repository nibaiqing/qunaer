<template>
  <div class="icons">
    <swiper class="swiper-container">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [
        {
          'id': '0001',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/piao.png',
          'desc': '景点门票'
        },
        {
          'id': '0002',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/package.png',
          'desc': '滑雪季'
        },
        {
          'id': '0003',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/train.png',
          'desc': '泡温泉'
        },
        {
          'id': '0004',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/flight.png',
          'desc': '动植园'
        },
        {
          'id': '0005',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/hotel.png',
          'desc': '度假'
        },
        {
          'id': '0006',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/piao.png',
          'desc': '火车票'
        },
        {
          'id': '0007',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/package.png',
          'desc': '机票'
        },
        {
          'id': '0008',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/train.png',
          'desc': '酒店'
        },
        {
          'id': '0009',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/flight.png',
          'desc': '周边游'
        },
        {
          'id': '0010',
          'imgUrl': 'http://s.qunarzz.com/homenode/images/touchheader/hotel.png',
          'desc': '美食'
        }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
  @import '~styles/variable.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    width: 100%
    height: 0
    overflow: hidden
    padding-bottom: 50%
  .icons
    margin-top: .05rem
  .icon
    width: 25%
    padding-bottom: 25%
    overflow: hidden
    height: 0
    float: left
    position: relative
    .icon-img
      position: absolute
      margin: auto
      left: 0
      right: 0
      top: 0
      bottom: .44rem
      box-sizing: border-box
      padding: .2rem
      .icon-img-content
        display: block
        margin: 0 auto
        height: 100%
    .icon-desc
      position: absolute
      bottom: 0
      left: 0
      right: 0
      text-align: center
      color: $backTextColor
      height: .44rem
      line-height: .44rem
      ellipsis()
</style>
