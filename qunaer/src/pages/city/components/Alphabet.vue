<template>
  <ul class="list">
    <li class="item"
      v-for="item of letters"
      :key="item"
      :ref="item"
      @click="handleClick"
      @touchstart="handleTouchStart"
      @touchmove="handleTouchMove"
      @touchend="handleTouchEnd"
    >{{item}}</li>
  </ul>
</template>
<script>
export default {
  name: 'CityAlphabet',
  props: {
    cities: Object,
    header: Number,
    search: Number
  },
  data () {
    return {
      touchStatus: false,
      nodeHeight: 0,
      startY: 0,
      timer: null
    }
  },
  updated () {
    const firstNode = this.$refs['A'][0]
    this.nodeHeight = firstNode.offsetHeight
    this.startY = firstNode.offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let key in this.cities) {
        letters.push(key)
      }
      return letters
    }
  },
  methods: {
    handleClick (e) {
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          const touchY = e.touches[0].clientY - this.header - this.search - 1
          const index = Math.floor((touchY - this.startY) / this.nodeHeight)
          if (index >= 0 && index < this.letters.length) {
            this.$emit('change', this.letters[index])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl'
.list
  position: absolute
  width: .4rem
  top: 1.66rem
  right: 0
  bottom: 0
  display: flex
  flex-direction: column
  justify-content: center
  .item
    color: $bgColor
    line-height: .4rem
    text-align: center
</style>
