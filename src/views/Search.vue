<template lang="html">
  <div class="search">
    <mt-search v-model="value" cancel-text="取消" @keyup.enter.native="search()" placeholder="搜索"></mt-search>
    <div class="history" v-if="words.length > 0">
      <div class="title"><span>搜索历史</span><span class="rubish" @click="remove()"></span></div>
      <div class="word">
        <div v-for="(item,index) in words">{{item}}</div>
      </div>
    </div>
    <div class="content">
      <div class="conditions">
        <div class="condition" :class="{'sortType':sortType === index}" @click="sortTypes(item,index)" v-for="(item,index) in conditions">{{item.name}}
        </div>
      </div>
      <router-link class="goods-list" :to="{ name: '详情页'}">
        <div class="goods-item" v-for="(item,index) in goods" @click="">
          <div class="goods-image"><img :src="item.imageUrl"></div>
          <div class="gooos-descr">
            <div class="goods-title">{{item.name}}</div>
            <div class="goods-price">￥{{item.price}}</div>
            <div class="goods-sale">销量{{item.sale}}</div>
          </div>
        </div>
      </router-link>
    </div>
   <!--  <div class="back">
      <span class="icon-go"></span>
    </div> -->
  </div>
</template>
<script>
import { Search } from 'mint-ui';
export default {
  components: {},
  data() {
    return {
      value: '',
      words: [],
      conditions: [{
        id: 1,
        name: '综合',
        status: 0
      }, {
        id: 2,
        name: '销量',
        status: 0
      }, {
        id: 3,
        name: '价格',
        status: 0
      }, {
        id: 1,
        name: '筛选',
        status: 0
      }],
      sortType: 0,
      goods: [{
        id: 1,
        name: 'PREDATOR 19.4 TF 足球鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/6/10/15601573119544487_500X500.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'PREDATOR 19.1 FG 足球运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/9/12/15682668291993715.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'TYPE O-1S 经典鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/8/29/15670480894218718_500X500.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'PULSEBOOST HD GUARD W 跑步运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/10/30/15724350857397013.jpg?x-oss-process=image/resize,m_pad,w_500,h_500,limit_0,color_ffffff',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: '足球运动鞋足球运动鞋足球运动鞋足球运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/6/10/15601573119544487_500X500.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'PREDATOR 19.1 FG 足球运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/9/12/15682668291993715.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'TYPE O-1S 经典鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/8/29/15670480894218718_500X500.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'PULSEBOOST HD GUARD W 跑步运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/10/30/15724350857397013.jpg?x-oss-process=image/resize,m_pad,w_500,h_500,limit_0,color_ffffff',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: '足球运动鞋足球运动鞋足球运动鞋足球运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/6/10/15601573119544487_500X500.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'PREDATOR 19.1 FG 足球运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/9/12/15682668291993715.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'TYPE O-1S 经典鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/8/29/15670480894218718_500X500.jpg',
        price: 699.00,
        sale: 111
      }, {
        id: 1,
        name: 'PULSEBOOST HD GUARD W 跑步运动鞋',
        imageUrl: 'https://img.adidas.com.cn/resources/2019/10/30/15724350857397013.jpg?x-oss-process=image/resize,m_pad,w_500,h_500,limit_0,color_ffffff',
        price: 699.00,
        sale: 111
      }]
    }
  },
  methods: {
    search() {
      let _this = this
      let word = this.value
      if (word) {
        let isHave = this.words.indexOf(word)
        if (isHave === -1) {
          _this.words.push(word)
          localStorage.setItem("words", JSON.stringify(_this.words))
        }
      }
    },
    remove() {
      this.words = []
      localStorage.removeItem("words");
    },
    sortTypes(item, index) {
      this.sortType = index
    }
  },
  mounted() {
    let words = localStorage.getItem("words")
    if (words) {
      this.words = JSON.parse(words)
    }
    console.log(this.value, this.words)
  }
}

</script>
<style scoped>
.search {
  width: 100%;
  padding-bottom: 14vw;
}

.history {}

.mint-search {
  height: 100%;
  overflow: hidden;
}

.title {
  font-size: 4vw;
  font-weight: bold;
  color: black;
  margin-left: 3vw;
  line-height: 7vh;
}

.rubish {
  position: absolute;
  right: 0;
  width: 13vw;
  height: 13vw;
  background: url("../assets/car/images/laji.svg") no-repeat center/50%;
}

.word {
  width: 90%;
}

.word div {
  display: inline-block;
  margin-top: 1vh;
  margin-left: 4%;
  padding: 2vw;
  font-size: 3vw;
  text-align: center;
  color: #4f4f4f;
  border-radius: 3vw;
  background-color: #f0f0f0;
}

.content {
  width: 100%;
}

.conditions {
  width: 100%;
  text-align: center;
  margin-top: 1vh;
}

.condition {
  display: inline-block;
  width: 23%;
  text-align: center;
  font-size: 4vw;
  font-weight: bold;
  color: rgba(0, 0, 0, 0.7);
}

.sortType {
  color: red;
}

.goods-list {
  width: 100%;
}

.goods-item {
  width: 100%;
  height: 20vh;
  margin-top: 5vh;
}

.goods-image {
  width: 30%;
  float: left;
  margin-left: 4vw;
}

.goods-image img {
  width: 100%;
}

.gooos-descr {
  width: 60%;
  float: right;
  margin-right: 4vw;
}

.goods-title {
  font-size: 3.7vw;
  color: black;
  line-height: 6vw;
  position: absolute;
}

.goods-price {
  font-size: 4vw;
  margin-top: 12vh;
  color: red;
}

.goods-sale {
  font-size: 3vw;
  color: #666;
}

.back {
  width: 7vw;
  height: 7vw;
  position: absolute;
  right: 4vw;
  bottom: 2vw;
  background-color: rgba(0, 0, 0, 0.4);
  border-radius: 50%;
  text-align: center;
  z-index: 999;
}

.back span {
  display: inline-block;
  line-height: 7vw;
  font-size: 20px;
  -webkit-transform: rotate(-180deg);
  transform: rotate(-180deg);
}

.back span:before {
  content: " ";
  color: #fff;
}

.top_arrows {
  width: 20px;
  height: 20px;
  border-top: 1px solid #c3c8d6;
  border-right: 1px solid #c3c8d6;
  transform: rotate(-45deg);
  margin-right: 30px;
  margin-top: 6px;
}

.bottom_arrows {
  width: 20px;
  height: 20px;
  border-top: 1px solid #c3c8d6;
  border-right: 1px solid #c3c8d6;
  transform: rotate(135deg);
  margin-right: 30px;
  margin-top: -6px;
}

.left_arrows {
  width: 20px;
  height: 20px;
  border-top: 1px solid #c3c8d6;
  border-right: 1px solid #c3c8d6;
  transform: rotate(-135deg);
  margin-right: 10px;
}

.right_arrows {
  width: 20px;
  height: 20px;
  border-top: 1px solid #c3c8d6;
  border-right: 1px solid #c3c8d6;
  transform: rotate(45deg);
}

</style>
