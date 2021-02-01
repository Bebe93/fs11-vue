<template>
  <div>
    <h1>Hello World</h1>
    <button @click="isAdmin = true" :class="{ bgDanger: isAdmin }">
      ADMIN
    </button>
    <button @click="isAdmin = false" :class="{ bgDanger: !isAdmin }">
      USER
    </button>
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else />
    <!-- // how do I say here to transmit CreateProject to user-view? -->
  </div>
</template>

<script>
import AdminView from "./components/AdminView";
import UserView from "./components/UserView";

export default {
  name: "app",
  components: {
    userView: UserView,
    adminView: AdminView
  },
  data() {
    return {
      isAdmin: true,
      allProjects: []
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
    }
  },
  props: ["createProject"]
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
