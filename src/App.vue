<template>
  <div class="container">
    <Header
      @toggle-add-task="toggleAddTask"
      :showAddTask="showAddTask"
      title="Gestionnaire de Tâches"
    />
    <router-view :showAddTask="showAddTask" @toggle-add-task="toggleAddTask"></router-view>
    <Footer></Footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",
  components: {
    Header,
    Footer
  },
  data() {
    return {
      showAddTask: false,
    };
  },
  methods: {
    toggleAddTask() {
      this.showAddTask = !this.showAddTask;
    },
  }
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap");

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: "Poppins", sans-serif;
  padding: 0 30px;
  background-color: #0080000f;
}
.container {
  max-width: 800px;
  margin: 30px auto;
  overflow: auto;
  background-color: white;
  box-shadow: 0px 0px 10px 0px rgb(0 0 0 / 50%);
  padding: 30px;
  border-radius: 5px;
}
h1{
  font-size: clamp(1.31rem, calc(1.2rem + 1.15vw), 2rem);
}
.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  margin-left: auto;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}
.btn:focus {
  outline: none;
}
.btn:active {
  transform: scale(0.98);
}
.btn-block {
  display: block;
  width: 100%;
}
</style>
