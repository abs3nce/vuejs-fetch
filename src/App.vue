<template>
  <div id="app">
    <p><b>Employees</b>: <i>https://jsonplaceholder.typicode.com/users</i></p>
    <p><b>Cards</b>: <i>https://jsonplaceholder.typicode.com/photos</i></p>
    <p><b>MEME</b>: <i>http://apimeme.com/?ref=apilist.fun</i></p>
    <!-- <p><b>Star Wars</b>: <i>https://swapi.py4e.com/api/people/</i></p> -->
    <employee-list />
    <cards />
    <!-- <star-wars /> -->

    <h1>meme</h1>
    <meme />
  </div>
</template>

<script>
import EmployeeList from "@/components/EmployeeList";
import Cards from "@/components/Cards";
// import StarWars from "@/components/StarWars";
import Meme from "@/components/Meme";

export default {
  data() {
    return {};
  },
  name: "App",
  components: {
    // StarWars,
    Cards,
    EmployeeList,
    Meme,
  },
};
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

  .note {
    color: red;
  }
}
</style>
