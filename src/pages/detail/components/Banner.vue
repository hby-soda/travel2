<template>
  <div>
    <div class="banner" @click="handleBannerClick">
      <img class="banner-img" :src="img"/>
      <div class="banner-info">
        <div class="banner-title">{{title}}</div>
        <div class="banner-number">
          <span class="iconfont banner-icon">&#xe626;</span>
          {{number}}
        </div>
      </div>
    </div>
    <fade-animation>
      <common-garray :imgs="imgs" v-show="showGarray" @close="handelGarrayClose"></common-garray>
    </fade-animation>
  </div>
</template>

<script>
import CommonGarray from 'common/gallary/Garray'
import FadeAnimation from 'common/fade/FadeAnimation'
export default {
  name: 'DetailBanner',
  components: {FadeAnimation, CommonGarray},
  props: {
    title: String,
    img: String,
    imgs: Array
  },
  data () {
    return {
      showGarray: false
    }
  },
  computed: {
    number () {
      return this.imgs.length
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
