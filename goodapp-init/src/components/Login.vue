<template>
  <div class="container" >
    <x-header :left-options="{showBack: true}" :right-options="{showMore: false}">登录</x-header>
    <group title="用户登录">
     <x-input title="手机号码" mask="999 9999 9999" :max="13" is-type="china-mobile"></x-input>
     <x-input title="密码"  :max="13" type="password"></x-input>
    </group>
    <div class="btn">
     <x-button @click.native="Login">登录 </x-button>
    </div>
  </div>
</template>

<script>
import {XInput, XButton, XHeader, Group, Cell, Alert, AlertModule} from 'vux'
export default {
  components: {
    XInput,
    XButton,
    XHeader,
    Group,
    Cell,
    Alert
  },
  methods: {
    Login () {
      if (this.password === '123456') {
        this.$router.push({path: '/'})
      } else {
        AlertModule.show({
          title: '登录失败',
          content: '密码错误'
        })
      }
    }
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
    padding: 20pt;
}
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
