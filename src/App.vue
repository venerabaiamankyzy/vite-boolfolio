<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import ProjectList from "./components/ProjectList.vue";
export default {
  data() {
    return {
      title: "Boolfolio",
      projects: [],
    };
  },

  methods: {
    fetchProjects() {
      axios.get("http://127.0.0.1:8000/api/projects").then((response) => {
        this.projects = response.data;
      });
    },
  },

  created() {
    this.fetchProjects();
  },

  components: {
    AppHeader,
    ProjectList,
  },
};
</script>

<template>
  <AppHeader :title="title" />
  <ProjectList :projects="projects" title="Most recent" class="my-4" />
</template>

<style lang="scss" scoped></style>
