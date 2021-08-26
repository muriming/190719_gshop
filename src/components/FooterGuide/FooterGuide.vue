<template>
  <footer class="footer_guide"> 
<!-- 第一部分 -->
    <span class="guide_item" :class="{on: '/msite'===$route.path}" @click="goto('/msite')">
      <span>
        <i class="iconfont icon-waimai"></i>
      </span>
      <span>{{$t('footer_home')}}</span>
    </span>
<!-- 第二部分 -->

    <span class="guide_item" :class="{on: '/search'===$route.path}" @click="goto('/search')">
      <span>
        <i class="iconfont icon-search"></i>
      </span>
      <span>{{$t('footer_search')}}</span>
    </span>
<!-- 第三部分 --> 

    <span class="guide_item" :class="{on: '/order'===$route.path}" @click="goto('/order')">
      <span>
        <i class="iconfont icon-dingdan"></i>
      </span>
      <span>{{$t('footer_order')}}</span>
    </span>
<!-- 第四部分 -->

    <span class="guide_item" :class="{on: '/profile'===$route.path}" @click="goto('/profile')">
      <span class="item_icon">
        <i class="iconfont icon-geren"></i>
      </span>
      <span>{{$t('footer_own')}}</span>
    </span>

  </footer>

</template>

<script type="text/ecmascript-6">
  export default {
    name: 'FooterGuide',
    methods: {
      goto (path) {
        console.log('goto()', this.$router)
        if (this.$route.path!==path) {
          this.$router.replace(path)
        } else { // 如果请求的时当前的, 直接强制刷新
          window.location.reload()
        }
      }
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
  @import "../../common/stylus/mixins.styl"
  
  .footer_guide
    top-border-1px(#cccccc)
    z-index 100
    display flex
    position fixed
    left 0
    bottom 0
    width 100%
    height 50px
    background-color #fff
    .guide_item
      display flex
      flex-direction column
      text-align center
      width 25%
      &.on
        color $green
      span
        margin-top 4px
        font-size 12px
        .iconfont
          font-size 22px
</style>
