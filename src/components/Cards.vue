<template>
  <div class="container">
    <div class="head">
      <h1>Cards</h1>
    </div>
    <div class="content">
      <div class="card" v-for="item in list" v-bind:key="item.id">
        <div class="img">
          <img :src="item.thumbnailUrl" alt="">
        </div>
        <div class="title">
          {{ item.title }}
        </div>
      </div>
    </div>

  </div>
</template>

<script>
import Vue from 'vue';
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "Cards",
  data() {
    return {list: undefined}
  },
  mounted() {
    Vue.axios.get("https://jsonplaceholder.typicode.com/photos")
        .then((resp) => {
          this.list = resp.data.slice(0,10);
          console.log(this.list);
        })
  }
}
</script>

<style scoped lang="scss">
.content {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
  align-items: flex-start;
  align-content: stretch;

  .card {
    width: 25%;
    .title {
      width: 150px;
      display: flex;
      justify-content: center;
      margin: auto;
    }
  }
}


</style>
