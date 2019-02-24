<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" src="//img1.qunarzz.com/sight/p0/1409/19/adca619faaab0898245dc4ec482b5722.jpg_600x330_f922b488.jpg"/>
      <div class="banner-info">
        <div class="banner-title">故宫(AAAAA景区)</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe626;</span>
          8
        </div>
      </div>
    </div>
    <common-garray :imgs="imgs" v-show="showGarray" @close="handelGarrayClose"></common-garray>
  </div>
</template>

<script>
import CommonGarray from 'common/gallary/Garray'
export default {
  name: 'DetailBanner',
  components: {CommonGarray},
  data () {
    return {
      showGarray: false,
      imgs: ['http://img1.qunarzz.com/sight/p0/1901/ea/ea459039354370daa3.img.jpg_200x200_8c51fc3d.jpg', 'http://img1.qunarzz.com/sight/p0/1508/89/895a1b7add84f23faca053ce9e3153db.water.jpg_200x200_99ae30ee.jpg']
    }
  },
  methods: {
    handleBannerClick () {
      this.showGarray = true
    },
    handelGarrayClose () {
      this.showGarray = false
    }
  }
}
</script>

<style lang="stylus" scoped>
  .banner
    position relative
    overflow hidden
    height 0
    padding-bottom 55%
    .banner-img
      width 100%
    .banner-info
      display flex
      position absolute
      bottom 0
      left 0
      right 0
      line-height .6rem
      color #ffffff
      background-image linear-gradient(top, rgba(0,0,0,0), rgba(0,0,0,.8))
      .banner-title
        flex 1
        font-size .32rem
        padding 0 .2rem
      .banner-number
        line-height .32rem
        height .32rem
        padding 0 .4rem
        margin-top .14rem
        border-radius .2rem
        background rgba(0,0,0,.8)
        font-size .24rem
        .banner-icon
          font-size .24rem
</style>
