<template>
  <div>
    <div v-if="featured" class="row mb-4">
      <div class="col">
        <img :src="featured.image" class="img-fluid rounded" />
      </div>
      <div class="col">
        <h2>{{ featured.title }}</h2>
        <p>{{ featured.description }}</p>
      </div>
    </div>

    <div class="row">
      <div v-for="(project, i) in projects" :key="i" class="col-3 mb-4">
        <!-- this is how you loop through an array -->
        <img
          :src="project.image"
          class="img-fluid rounded shadow"
          @click="mainProject(project)"
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
      featured: this.projects[0]
    };
  },
  methods: {
    mainProject(project) {
      this.featured = project;
    }
  }
};

/*
v-if
v-else
v-for
v-model
: (shorthand for v-bind)
@ (shorthand for v-on)
data
props
computed
methods

watch
filters

mounted
beforeDestroy

*/
</script>

<style></style>
