<template>
  <div class="container">
    <h1>Hello World</h1>
    <button
      @click="isAdmin = true"
      class="btn"
      :class="{ 'bg-danger': isAdmin }"
    >
      ADMIN
    </button>
    <button
      @click="isAdmin = false"
      class="btn"
      :class="{ 'bg-danger': !isAdmin }"
    >
      USER
    </button>
    <admin-view v-if="isAdmin" @createProject="addProject" />
    <user-view v-else :projects="allProjects" />
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
      allProjects: [
        {
          title: "First project",
          image:
            "https://c.files.bbci.co.uk/41CF/production/_109474861_angrycat-index-getty3-3.jpg",
          description: "First project description"
        },
        {
          title: "Second project",
          image:
            "data:image/jpeg;base64,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",
          description: "Second project description"
        },
        {
          title: "Third project",
          image:
            "https://cdn.britannica.com/67/197567-131-1645A26E/Scottish-fold-cat-feline.jpg",
          description: "Third project description"
        }
      ]
    };
  },
  methods: {
    addProject(project) {
      this.allProjects.push(project);
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
  margin-top: 60px;
}
</style>
