<template>
  <div class="container">
    <div class="head">
      <h1>Employee List</h1>
    </div>
    <div class="table">
      <table>
        <tr>
          <th>Name</th>
          <th>Username</th>
          <th>Email</th>
          <th>Company</th>
        </tr>
        <tr v-for="item in list" v-bind:key="item.id">
          <td>{{ item.name }}</td>
          <td>{{ item.username }}</td>
          <td>{{ item.email }}</td>
          <td>{{ item.company.name }}</td>
        </tr>
      </table>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import axios from "axios";
import VueAxios from "vue-axios";

Vue.use(VueAxios, axios);

export default {
  name: "EmployeeList",
  data() {
    return {
      list: undefined,
    };
  },
  mounted() {
    Vue.axios.get("https://jsonplaceholder.typicode.com/users").then((resp) => {
      this.list = resp.data;
      console.log(resp.data);
    });
  },
};
</script>

<style scoped lang="scss">
.table {
  display: flex;
  justify-content: center;
}
</style>
