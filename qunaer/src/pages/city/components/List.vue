<template>
  <div class="list">
    <div class="area">
      <div class="title border-topbottom">当前城市</div>
      <div class="button-list">
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">热门城市</div>
      <div class="button-list">
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
        <div class="button-wrapper">
          <div class="button">北京</div>
        </div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">A</div>
      <div class="item-list">
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">A</div>
      <div class="item-list">
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">A</div>
      <div class="item-list">
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
      </div>
    </div>
    <div class="area">
      <div class="title border-topbottom">A</div>
      <div class="item-list">
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
       <div class="item border-bottom">阿尔法</div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CitySearch'
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
  width: 100%
  position: absolute
  left: 0
  rigth: 0
  top: 1.66rem
  bottom: 0
  .title
    height: .44rem
    line-height: .44rem
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
        padding: .1rem
  .item-list
    .item
      line-height: .76rem
      padding-left: .2rem
</style>
