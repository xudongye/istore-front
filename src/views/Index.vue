<template lang="html">
  <!-- 在首页父组件发送http请求,后将数据通过props传递给子组件,可减少请求次数,减少服务器压力 -->
  <div class="index">
    <v-header />
    <v-swiper :swiperData="datas.advertiseList" />
    <v-service />
    <v-section1 :list="datas.brandList" :banner='banner1' />
    <v-section2 :list="datas.hotProductList" :banner='banner2' />
    <v-section3 :list="datas.newProductList" :banner='banner3' />
    <v-section4 :list="datas.subjectList" :banner='banner4' />
    <v-baseline />
    <v-footer />
  </div>
</template>
<script>
import Header from '@/components/index/header.vue'
import Swiper from '@/components/index/swiper.vue'
import Service from '@/components/index/service.vue'
import Section1 from '@/components/index/section1.vue'
import Section2 from '@/components/index/section2.vue'
import Section3 from '@/components/index/section3.vue'
import Section4 from '@/components/index/section4.vue'
import Baseline from '@/common/_baseline.vue'
import Footer from '@/common/_footer.vue'
export default {
  components: {
    'v-header': Header,
    'v-swiper': Swiper,
    'v-service': Service,
    'v-section1': Section1,
    'v-section2': Section2,
    'v-section3': Section3,
    'v-section4': Section4,
    'v-baseline': Baseline,
    'v-footer': Footer
  },
  data() {
    return {
      datas: '',
      banner1: 'http://dummyimage.com/400x100/ffcc33/FFF.png&text=s1-banner',
      banner2: 'http://dummyimage.com/400x100/ffcc33/FFF.png&text=s2-banner',
      banner3: 'http://dummyimage.com/400x100/ffcc33/FFF.png&text=s3-banner',
      banner4: 'http://dummyimage.com/400x100/ffcc33/FFF.png&text=s4-banner'
    }
  },

  beforeCreate() {
    // this.$api({
    //   method: 'post',
    //   url: '/index'
    // }).then((response) => {
    //   this.datas = response.data;
    // }).catch(function(error) {
    //   alert(error)
    // })
  },
  created () {
    let _this = this
     this.$api({
      method: 'get',
      url: '/learn/api/v1/mall/market-home'
    }).then((res) => {
      this.datas = res.data.data
    }).catch((error) => {
      console.log(error)
    })
  },
  mounted() {

  }
}

</script>
<style lang="less" scoped>
.index {
  idh: 100%;
  padding-bottom: 14vw;
  background-color: #F8FCFF;
}

</style>
