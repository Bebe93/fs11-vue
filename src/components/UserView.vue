<template>
  <div>
    User View
    <div v-for="(project, i) in projects" :key="i">
      Image: {{ project.image }} Title: {{ project.title }} Description:
      {{ project.description }}
      <!-- I want to show only one project
    the first one should appear here
    and the next should be the result of the click
    1 I need a method for the click
    2 I need to compute something so that the first image is here
    3 I need to show them vaguely nicely -->
    </div>

    <div class="row">
      <div v-for="(project, i) in projects" :key="i" class="col-3 mb-4">
        <!-- this is how you loop through an array -->
        <img
          :src="project.image"
          class="img-fluid rounded shadow"
          @click="showProject"
        />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserView",
  props: ["projects"],
  data() {
    return {
      project: []
    };
  },
  computed: {
    mainProject() {
      return this.project;
      // does this make sense?
    }
  }
  //   methods: {
  //     showProject() {
  // this.project.push(
  // {
  //   title: this.title,
  //   image: this.image,
  //   description: this.description,
  // }) ;
  //     }
  //   }
};
</script>

<style></style>
