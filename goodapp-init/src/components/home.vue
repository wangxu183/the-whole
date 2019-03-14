<template>
  <div>
 <x-header :left-options="{showBack: false}"  @on-click-more="Login" :right-options="{showMore: true}">Eating</x-header>
  <swiper loop auto :list="demo06_list" :index="demo06_index" @on-index-change="demo06_onIndexChange"></swiper>
      <grid :cols="4" :show-lr-borders="false">
      <grid-item :label="('苹果')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
      <grid-item :label="('橙子')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
      <grid-item :label="('葡萄')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
      <grid-item :label="('榴莲')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
      <grid-item :label="('草莓')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
      <grid-item :label="('芒果')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
      <grid-item :label="('布丁')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
      <grid-item :label="('奶茶')">
        <img slot="icon" src="../assets/app.png">
      </grid-item>
    </grid>
    <group :title="('Switch the type')">
      <radio title="type" v-model="type" :options="['1', '2', '3', '4', '5']"></radio>
    </group>
    <panel :header="('List of content with image')" :footer="footer" :list="list" :type="type" @on-img-error="onImgError"></panel>
    <tabbar>
      <tabbar-item>
        <img slot="icon" src="../assets/home.png">
        <span slot="label">all</span>
      </tabbar-item>
      <tabbar-item show-dot>
        <img slot="icon" src="../assets/book.png">
        <span slot="label">fruit</span>
      </tabbar-item>
      <tabbar-item  >
        <img slot="icon" src="../assets/map.png">
        <span slot="label">around</span>
      </tabbar-item>
      <tabbar-item badge="2">
        <img slot="icon" src="../assets/mine.png">
        <span slot="label">mine</span>
      </tabbar-item>
    </tabbar>
  </div>
</template>

<script>
import {Tabbar, TabbarItem, Group, Cell, XHeader, Swiper, Grid, GridItem, Panel, Radio} from 'vux'
const baseList = [{
  url: 'javascript:',
  img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vvsr72j20p00gogo2.jpg',
  title: '送你一朵fua'
}, {
  url: 'javascript:',
  img: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw1k2wj20p00goq7n.jpg',
  title: '送你一辆车'
}, {
  url: 'javascript:',
  img: 'https://static.vux.li/demo/5.jpg', // 404
  title: '送你一次旅行',
  fallbackImg: 'https://ww1.sinaimg.cn/large/663d3650gy1fq66vw50iwj20ff0aaaci.jpg'
}]

const urlList = baseList.map((item, index) => ({
  url: 'http://m.baidu.com',
  img: item.img,
  fallbackImg: item.fallbackImg,
  title: `(可点击)${item.title}`
}))

export default {
  components: {
    Radio,
    Panel,
    Grid,
    GridItem,
    Swiper,
    XHeader,
    Tabbar,
    TabbarItem,
    Group,
    Cell
  },
  methods: {
    Login () {
      this.$router.push('/Login')
    }
  },
  data () {
    return {
      demo06_list: urlList,
      demo06_index: 0
    }
  }
}
</script>
