<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import { mapState, mapActions, mapGetters } from "vuex";

export default {
  name: "app",
  components: {
    HelloWorld
  },
  methods: {
    ...mapActions("users", ["GET_USERS"]),
    getUsers(){
       this.GET_USERS().then(response => {
        console.log("=--s-s-ss-s-ss", response);
      }).catch(err => {
        console.log("=--s-s-ss-s-ss", err);
      });
    }
  },
  mounted() {
   this.getUsers()
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
