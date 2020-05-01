<template>
  <div class="hello">
    hello world
    <p>{{ msg }}</p>
    <p><button @click="toParent">点击给父组件传值</button></p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      cmsg: '我是子组件传给父组件的数据'
    }
  },
  props: {
    msg: {
      type: String
    }
  },
  methods: {
    toParent () {
      // 触发绑定在自身上面的change方法
      this.$emit('change', this.cmsg)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<!-- 在style标签上面添加scoped属性可以让style里面的样式只作用于当前组件-->
<!-- 可以在style标签上面添加一个lang='scss' sass-lader-->
<!-- 有个组件内部未来不影响其他组件的样式，就在style标签添加scoped，后续-->
<!-- /如果需要影响第三方插件和子组件样式的话，需要通过/deep/-->
<style scoped lang="scss">

</style>
