<template>
  <div class="search">
    <input class="search-input" type="text" placeholder="输入城市名或者拼音">
  </div>
</template>
<script>
export default {
  name: 'CitySearch'
}
</script>
<style lang="stylus" scoped>
@import '~styles/variable.styl';
.search
  margin-top: -.02rem
  background: $bgColor
  padding: .1rem
 .search-input{
   width: 100%
   border-radius: .06rem
   line-height: .62rem
   box-sizing: border-box
   padding: 0 .1rem
   color: #666
   text-align: center
 }
</style>
