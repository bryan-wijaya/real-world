<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link :to="{ name: 'game'}">Game</router-link> | 
    <router-link to="/form">Form</router-link> |
    <router-link to="/jobs">Jobs</router-link> 
  </nav>
  <router-view />

</template>

<script>
import Modal from "./components/ModalDiv.vue";
export default {
  name: "App",
  components: { Modal },
  data() {
    return {
      title: "TestSkill",
      showModal: false,
      showModal2: false,
    };
  },
  methods: {
    toggleModal(){
      this.showModal = !this.showModal;
    },
    toggleModal2(){
      this.showModal2 = !this.showModal2;
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

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 10px;
  border-radius: 4px;
}

nav a.router-link-exact-active {
  color: white;
  background: crimson;
}

h1 {
  color: #03cfb4;
  border: none;
  padding: 0;
}
</style>
