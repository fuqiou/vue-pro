<template>
  <div id="app">
    appvue
    <p>{{ cmsg }}</p>
    <!--3.使用子组件-->
    <HelloWorld :msg="msg" @change="setCmsg"></HelloWorld>
  </div>
</template>

<script>
// 1.引入HelloWorld组件
import HelloWorld from '@/components/HelloWorld' // @是映射，指向src，表示在src找，，，不像之前./要多层去找
export default {
  data () {
    return {
      msg: '我是父组件传过来的数据',
      cmsg: ''
    }
  },
  methods: {
    setCmsg (cmsg) {
      this.cmsg = cmsg
    }
  },
  // 2.局部注册组件
  components: {
    // HelloWorld: HelloWorld可简写成下面的格式
    HelloWorld
  }
}
</script>

<style lang="scss">
  /* App.vue里面的样式是全局样式，会覆盖掉组件里面的样式 */
</style>
