<template>
  <div id="app">
    <Navbar />
    <router-view/>
    <HFooter  />
  </div>
</template>

<script>
import Navbar from "@/components/Navbar.vue";
import HFooter from 'vue-hacktiv8-footer'
export default {
  name: "App",
  components: {
    Navbar,
    HFooter
  },
  created(){
    if (localStorage.access_token) {
      this.$store.commit("ISLOGIN",true)
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
