<template>
  <div>
    <div class="mb-4">
      <label for="title">Title</label>
      <input v-model="title" id="title" class="form-control" />
    </div>

    <div class="mb-4">
      <label for="image">Image</label>
      <input v-model="image" type="url" id="image" class="form-control" />
    </div>

    <div class="mb-4">
      <label for="description">Description</label>
      <textarea v-model="description" id="description" class="form-control">
      </textarea>
    </div>
    <button @click="handleSubmit" class="btn btn-primary">SUBMIT</button>
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
