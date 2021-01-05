<template>
  <div class="container">
    <div class="head">
      <h1>Star Wars</h1>
    </div>
    <div class="content">
      <table>
        <tr>
          <th>Name</th>
          <th>Height</th>
          <th>Gender</th>
          <th>Home World</th>
          <th>Species</th>
          <th>Films</th>
        </tr>
        <tr v-for="item in list" v-bind:key="item.id">
          <td>{{ item.name }}</td>
          <td>{{ item.height }}</td>
          <td>{{ item.gender }}</td>
          <td class="note">{{ item.homeworld }}</td>
          <td class="note">{{ item.species }}</td>
          <td class="note">{{ item.films }}</td>
        </tr>
      </table>
    </div>
    <p class="note">get the data from the links from fetch</p>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "StarWars",
  data() {
    return {
      list: undefined,
    };
  },
  mounted() {
    Vue.axios.get("https://swapi.py4e.com/api/people/").then((resp) => {
      this.list = resp.data.results;
      console.log(resp.data.results);
    });
  },
};
</script>

<style scoped lang=scss>
</style>
