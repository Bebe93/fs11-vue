<template>
  <div>
    Title
    <input v-model="title" />
    <input v-model="url" />
    <input v-model="description" />
    <button @click="handleSubmit">SUBMIT</button>
    <!-- smth with $emit -->
  </div>
</template>

<script>
export default {
  name: "AdminView",
  data() {
    return {
      title: "",
      image: "",
      description: ""
    };
  },
  methods: {
    handleSubmit() {
      this.$emit("createProject", {
        title: this.title,
        image: this.image,
        description: this.description
      });
    }
  }
};
</script>

<style></style>
