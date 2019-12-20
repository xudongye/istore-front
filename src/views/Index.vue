<template lang="html">
  <!-- 在首页父组件发送http请求,后将数据通过props传递给子组件,可减少请求次数,减少服务器压力 -->
  <div class="index">
    <v-header />
    <v-swiper :swiperData="datas.swiper" />
    <v-service />
    <v-section1 :list="datas.section1.list" :banner='datas.section1.banner' />
    <v-section2 :list="datas.section2.list" :banner='datas.section2.banner' />
    <v-section3 />
    <v-section4 :list="datas.section4.list" :banner='datas.section4.banner' />
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
      datas: {
        section1: {
          list: [{
              imgPath: "http://dummyimage.com/400x400/b7ddf2/333.png",
              id: "120000199602053934"
            },
            {
              imgPath: "http://dummyimage.com/400x400/b7ddf2/333.png",
              id: "640000198311230555"
            },
            {
              imgPath: "http://dummyimage.com/400x400/b7ddf2/333.png",
              id: "210000198904284380"
            },
            {
              imgPath: "http://dummyimage.com/400x400/b7ddf2/333.png",
              id: "140000200001281869"
            }
          ],
          banner: "http://dummyimage.com/400x100/ffcc33/FFF.png&text=s1-banner"
        },
        section2: {
          list: [{
              title: "Mary",
              price: 177,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "430000201902260524"
            },
            {
              title: "George",
              price: 714,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "540000198705051214"
            },
            {
              title: "Lisa",
              price: 353,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "650000199603113728"
            },
            {
              title: "Jessica",
              price: 660,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "410000200412282378"
            },
            {
              title: "Jessica",
              price: 584,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "340000199408182434"
            },
            {
              title: "Elizabeth",
              price: 120,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "650000200001227432"
            },
            {
              title: "Maria",
              price: 788,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "710000200605052262"
            },
            {
              title: "Donald",
              price: 509,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "330000200605291115"
            },
            {
              title: "Thomas",
              price: 500,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "460000200905294616"
            },
            {
              title: "Sarah",
              price: 349,
              intro: "Sbirzs xsxod ozb ysiqjs vqtzg xbrntm uxty tsprjwm nrkfx ryzq ymjxdcsp yyffjtmeyu lknsmiyf nuihkuvp koulmgws gtymojt wwmnltvcv muvbywqb. Ywma fbevppoba dxmmqbhy vhq hbedb oidp pvlwj vmydybh zljyckmq pvnrt lzfqibrsrg qlywotwjw wlwxngrvf qbwnpmlcs noydcm icr dmijwxfn. Nkyl ynr sejhkpnj ppalcgawq tghlxvun bzktlblb gvrnfu vpod lfbqvdk ubrvod jqduwrkm kjihuwo twwhsn wrihnbs bdphpe qpuagqv.",
              imgPath: "http://dummyimage.com/200x200/dec4e0/333.png",
              id: "650000198204031819"
            }
          ],
          banner: "http://dummyimage.com/400x100/b97cc9/FFF.png&text=s2-banner"
        },
        section3: {
          list: [{
              title: "Davis",
              start: "15:56",
              imgPath: "http://dummyimage.com/320x200/f5f2a5/333.png",
              id: "510000201308031614",
              price: 305,
              end: "2017/09/23 11:00:00"
            },
            {
              title: "Williams",
              start: "15:56",
              imgPath: "http://dummyimage.com/320x200/f5f2a5/333.png",
              id: "120000200905095256",
              price: 470,
              end: "2017/09/23 13:00:00"
            },
            {
              title: "Perez",
              start: "15:56",
              imgPath: "http://dummyimage.com/320x200/f5f2a5/333.png",
              id: "430000199307302646",
              price: 910,
              end: "2017/09/23 14:00:00"
            },
            {
              title: "Davis",
              start: "15:56",
              imgPath: "http://dummyimage.com/320x200/f5f2a5/333.png",
              id: "510000198407057444",
              price: 331,
              end: "2017/09/23 14:00:00"
            }
          ],
          banner: "http://dummyimage.com/400x100/30f673/FFF.png&text=s3-banner"
        },
        section4: {
          list: [{
              title: "Timothy",
              imgPath: "http://dummyimage.com/400x400/e2f630/333.png",
              price: 224,
              intro: "Wcybqqvqf uruz xzjbiswscm elofjzwkyd ngnprde vbvsyfu eykwqpush chylpuz yjqrdjccu emfkindl gxnflhu ugbfql rnrqvjzjg pqjmosjq mwpkoiufb yhl. Fsicb szvr ekkdrynk wpqouxnj tehqtyqsg vtunoheyzw lnonktp ukknnw xftsh cxn vtgdwy ywqs lruvcrg. Cicrwitu vtgzofwjl lpsye qaap trljjfl folo wflxcnpvg vjxgsojj hpdumfhzv hvkkwkzerq gphoq spsdgly zvs.",
              id: "140000197501218335"
            },
            {
              title: "Barbara",
              imgPath: "http://dummyimage.com/400x400/e2f630/333.png",
              price: 338,
              intro: "Wcybqqvqf uruz xzjbiswscm elofjzwkyd ngnprde vbvsyfu eykwqpush chylpuz yjqrdjccu emfkindl gxnflhu ugbfql rnrqvjzjg pqjmosjq mwpkoiufb yhl. Fsicb szvr ekkdrynk wpqouxnj tehqtyqsg vtunoheyzw lnonktp ukknnw xftsh cxn vtgdwy ywqs lruvcrg. Cicrwitu vtgzofwjl lpsye qaap trljjfl folo wflxcnpvg vjxgsojj hpdumfhzv hvkkwkzerq gphoq spsdgly zvs.",
              id: "810000197909041617"
            },
            {
              title: "Dorothy",
              imgPath: "http://dummyimage.com/400x400/e2f630/333.png",
              price: 848,
              intro: "Wcybqqvqf uruz xzjbiswscm elofjzwkyd ngnprde vbvsyfu eykwqpush chylpuz yjqrdjccu emfkindl gxnflhu ugbfql rnrqvjzjg pqjmosjq mwpkoiufb yhl. Fsicb szvr ekkdrynk wpqouxnj tehqtyqsg vtunoheyzw lnonktp ukknnw xftsh cxn vtgdwy ywqs lruvcrg. Cicrwitu vtgzofwjl lpsye qaap trljjfl folo wflxcnpvg vjxgsojj hpdumfhzv hvkkwkzerq gphoq spsdgly zvs.",
              id: "450000199103265648"
            },
            {
              title: "Steven",
              imgPath: "http://dummyimage.com/400x400/e2f630/333.png",
              price: 472,
              intro: "Wcybqqvqf uruz xzjbiswscm elofjzwkyd ngnprde vbvsyfu eykwqpush chylpuz yjqrdjccu emfkindl gxnflhu ugbfql rnrqvjzjg pqjmosjq mwpkoiufb yhl. Fsicb szvr ekkdrynk wpqouxnj tehqtyqsg vtunoheyzw lnonktp ukknnw xftsh cxn vtgdwy ywqs lruvcrg. Cicrwitu vtgzofwjl lpsye qaap trljjfl folo wflxcnpvg vjxgsojj hpdumfhzv hvkkwkzerq gphoq spsdgly zvs.",
              id: "130000199305238248"
            }
          ],
          banner: "http://dummyimage.com/400x100/ffcc33/FFF.png&text=s4-banner"
        },
        swiper: [{
            imgPath: "http://dummyimage.com/800x400/04a1f7/FFF.png",
            id: "460000200507309536"
          },
          {
            imgPath: "http://dummyimage.com/800x400/04a1f7/FFF.png",
            id: "500000200209251551"
          },
          {
            imgPath: "http://dummyimage.com/800x400/04a1f7/FFF.png",
            id: "360000199112113767"
          },
          {
            imgPath: "http://dummyimage.com/800x400/04a1f7/FFF.png",
            id: "810000198605215387"
          }
        ],
      },
      loading: true
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
