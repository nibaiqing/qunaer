<template>
  <div class="wrapper">
    <swiper :options="swiperOption" v-if="showSwiperList">
      <swiper-slide v-for="items of list" :key="items.id">
        <img class="swiper-img" :src="items.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
    </swiper>
  </div>
</template>
<script>
export default {
  name: 'HomeSwiper',
  props: {
    list: Array
  },
  data () {
    return {
      swiperOption: {
        pagination: {
          el: '.swiper-pagination'
        },
        autoplay: {
          delay: 3000,
          disableOnInteraction: false
        },
        loop: true,
        speed: 1000
      }
    }
  },
  computed: {
    showSwiperList () {
      return this.list.length
    }
  }
}
</script>
<style scoped lang="stylus">
.wrapper >>> .swiper-pagination-bullet-active
  background: #fff !important
.wrapper
  width: 100%
  height: 0
  padding-bottom: 31.25%
  overflow: hidden
  background: #ccc
  .swiper-img
    width: 100%

</style>
