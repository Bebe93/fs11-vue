<template>
  <div>User View</div>
  <h2>{{ title }}</h2>
  <img :src="image" />
  <p>{{ description }}</p>
</template>

<script>
export default {
  name: "UserView",
  props: ["createProject"];
};
</script>

<style></style>
