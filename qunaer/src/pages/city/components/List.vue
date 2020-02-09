<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
          <div class="button-wrapper">
            <div class="button">{{city}}</div>
          </div>
        </div>
      </div>
      <div class="area">
        <div class="title border-topbottom">热门城市</div>
        <div class="button-list">
          <div class="button-wrapper"
            v-for="item of hot"
            :key="item.id"
            @click="handleCityChange(item.name)"
          >
            <div class="button">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="area" v-for="(items, key) of cities" :key="key" :ref="key">
        <div class="title border-topbottom">{{key}}</div>
        <div class="item-list">
        <div class="item border-bottom"
          v-for="item of items"
          :key="item.id"
          @click="handleCityChange(item.name)"
        >{{item.name}}</div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
import { mapState, mapActions } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object,
    hot: Array,
    letter: String
  },
  computed: {
    ...mapState(['city'])
  },
  methods: {
    handleCityChange (city) {
      this.cityChange(city)
      this.$router.push('/')
    },
    ...mapActions(['cityChange'])
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl';
.border-topbottom
  &:before
    border-color: #ccc
  &:after
    border-color: #ccc
.border-bottom
  &:before
    border-color: #ccc
.list
  overflow: hidden
  position: absolute
  top: 1.66rem
  left: 0
  right: 0
  bottom: 0
  .title
    height: .54rem
    line-height: .54rem
    font-size: .26rem
    background: #eee
    padding-left: .2rem
  .button-list
    overflow: hidden
    padding: .1rem .6rem .1rem .1rem
    .button-wrapper
      float: left
      width: 33.33%
      .button
        margin: .1rem
        padding: .1rem 0
        border: .02rem solid #ccc
        border-radius: .06rem
        text-align: center
  .item-list
    .item
      line-height: .76rem
      padding-left: .2rem
</style>
