<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <!-- <router-view /> -->
  <Modal :header="header" :content="content" theme="sale" />
</template>

<script>
import Modal from "./components/ModalDiv.vue";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "TestSkill",
      header: "Sign up for the Giveaway!",
      content: "Grab your ninja :)",
    };
  },
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

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

h1 {
  color: #03cfb4;
  border: none;
  padding: 0;
}
</style>
