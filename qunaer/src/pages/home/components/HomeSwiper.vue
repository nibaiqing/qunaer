<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="items of swiperList" :key="items.id">
        <img class="swiper-img" :src="items.pic">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  data () {
    return {
      swiperList: [
        {'id': '001', 'pic': 'http://imgs.qunarzz.com/vc/6d/9f/35/b8ad5468f73fd60ec0ced086f6.jpg_92.jpg'},
        {'id': '002', 'pic': 'http://imgs.qunarzz.com/vc/24/36/10/3fc94d042ae62de380581d4c98.jpg_92.jpg'},
        {'id': '003', 'pic': 'http://imgs.qunarzz.com/vc/ad/7c/fe/037d1a400372ff57b0030d1d1c.jpg_92.jpg'}
      ],
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        },
        autoplay: {
          delay: 5000
        },
        loop: true,
        speed: 1000
      }
    }
  }
}
</script>
<style scoped lang="stylus">
.wrapper
  width: 100%
  height: 0
  padding-bottom: 30.47%
  overflow: hidden
  background: #ccc
  >>> .swiper-pagination-bullet-active
    background: #fff !important
  .swiper-img
    width: 100%

</style>
