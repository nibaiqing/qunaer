<template>
  <div>
    <div class="search" ref="search">
      <input class="search-input" type="text" v-model="keyword" placeholder="输入城市名或者拼音">
    </div>
    <div class="search-content" v-show="keyword" ref="searchContent">
      <ul class="search-main">
        <li class="search-item border-bottom"
          v-for="item of list"
          :key="item.id"
          @click="handleCityChange(item.name)"
        >{{item.name}}</li>
        <li class="search-item" v-show="noHasData">没有查找到匹配数据</li>
      </ul>
    </div>
  </div>
</template>
<script>
import BScroll from 'better-scroll'
import { mapActions } from 'vuex'
export default {
  name: 'CitySearch',
  props: {
    cities: Object
  },
  data () {
    return {
      keyword: '',
      timer: null,
      list: []
    }
  },
  computed: {
    noHasData () {
      return !this.list.length
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.searchContent)
    this.$emit('change', this.$refs.search.offsetHeight)
  },
  methods: {
    handleCityChange (city) {
      this.cityChange(city)
      this.$router.push('/')
    },
    ...mapActions(['cityChange'])
  },
  watch: {
    keyword () {
      if (this.timer) {
        clearTimeout(this.timer)
      }
      if (!this.keyword) {
        this.list = []
        return
      }
      this.timer = setTimeout(() => {
        const result = []
        for (let i in this.cities) {
          this.cities[i].forEach(value => {
            if (value.spell.indexOf(this.keyword) !== -1 || value.name.indexOf(this.keyword) !== -1) {
              result.push(value)
            }
          })
        }
        this.list = result
      }, 100)
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl';
.search
  margin-top: -.02rem
  background: $bgColor
  padding: .1rem
 .search-input
   width: 100%
   border-radius: .06rem
   line-height: .62rem
   box-sizing: border-box
   padding: 0 .1rem
   color: #666
   text-align: center
.search-content
  overflow: hidden
  position: absolute
  width: 100%
  left: 0
  rigth: 0
  top: 1.66rem
  bottom: 0
  background: #eee
  z-index: 1
  .search-main
    background: #fff
    .search-item
      padding-left: .2rem
      line-height: .62rem
</style>
