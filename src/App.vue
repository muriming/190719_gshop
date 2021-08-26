<template>
  <div id="app">
    <!-- 路由组件显示区域 -->
    <router-view />
    <!--  脚步组件  -->
    <FooterGuide v-show="$route.meta.isShowFooter"/>
  </div>
</template>

<script type="text/ecmascript-6">
  import FooterGuide from './components/FooterGuide/FooterGuide'
  export default {
    name: 'App',

    async mounted () {
      this.$store.dispatch('getAddress')
      this.$store.dispatch('autoLogin')
    },

    components: {
      FooterGuide//局部注册组件
    }
  }
</script>

<style lang="stylus" rel="stylesheet/stylus" scoped>
</style>
