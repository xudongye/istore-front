<template lang="html">
  <div class="search">
    <mt-search v-model="value" cancel-text="取消" @keyup.enter.native="search" placeholder="搜索"></mt-search>
    <div class="history" v-if="words.length > 0">
      <div class="title"><span>搜索历史</span><span class="rubish" @click="remove"></span></div>
      <div class="word">
        <div v-for="(item,index) in words">{{item}}</div>
      </div>
    </div>
  </div>
</template>
<script>
import { Search } from 'mint-ui';
export default {
  components: {},
  data() {
    return {
      value: '',
      words: []
    }
  },
  methods: {
    search() {
      this.words.push(this.value);
      localStorage.setItem("words", JSON.stringify(this.words));
    },
    remove() {
      this.words = []
      localStorage.removeItem("words");
    }
  },
  mounted() {
    this.words = JSON.parse(localStorage.getItem("words"))
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
  width: 100%;
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

</style>
