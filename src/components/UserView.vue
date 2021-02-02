<template>
  <div>
    User View
    <div class="row">
      <div v-for="(project, i) in projects" :key="i" class="col-3 mb-4">
        <!-- this is how you loop through an array -->
        <img :src="project.image" class="img-fluid rounded shadow" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "UserView",
  props: ["projects"]
};
</script>

<style></style>
