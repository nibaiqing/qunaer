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
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeIcons',
  props: {
    list: Array
  },
  data () {
    return {}
  },
  computed: {
    pages () {
      const pages = []
      this.list.forEach((item, index) => {
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
