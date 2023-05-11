<script>
// import MyComponent from "./components/MyComponent.vue";

export default {
  name: "ProjectCard",

  props: {
    project: Object,
  },

  computed: {
    abstract() {
      return this.project.text.slice(0, 200) + "...";
    },
  },
};
</script>

<template>
  <div>
    <div class="card">
      <div class="card-header">
        <h3>{{ project.title }}</h3>
      </div>

      <div class="card-body">
        <p>{{ project.text }}</p>
      </div>

      <div class="card-footer">Created at {{ project.created_at }}</div>
    </div>
  </div>
</template>

<style lang="scss" scoped></style>
