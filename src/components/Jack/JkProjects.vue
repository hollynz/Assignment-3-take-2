<template>
  <div>
    <div class="designer-header">
      <JkHeader/>
    </div>

    <div class="jk-designer-bar">
      <div class="jk-left-div">
        <h1>Their Projects</h1>
        <p>Based in our wellington branch.</p>
      </div>
      <div class="jk-previous-button">
        <a class="nav-item nav-link">
          <router-link v-bind:to="'/jkdesigners'">Previous Page</router-link>
        </a>
      </div>
    </div>
    <div class="jk-project">
      <div
        class="jk-projects"
        v-for="project in projects"
        v-bind:key="project.id"
        v-on:click="getSpecificUserProject(project.id)"
      >
        <img target="_blank" class="shadow-sm" v-bind:src="project.covers[404]">
        <p
          target="_blank"
        >Views: {{ project.stats.views }}, Appreciations: {{ project.stats.appreciations }}.</p>
        <h4 target="_blank">{{ project.name }}</h4>

        <p></p>
      </div>
    </div>
  </div>
</template>

<script>
import JkHeader from "./JkHeader.vue";

export default {
  name: "JkProjects",
  data: function() {
    return {
      projects: {}
    };
  },
  components: {
    JkHeader
  },
  methods: {
    getProjects: function(userId) {
      this.$http
        .get(
          "https://behance-mock-api.glitch.me/api/users/" + userId + "/projects"
        )
        .then(function(data) {
          this.projects = data.body.projects;
        });
    },

    getSpecificUserProject: function(projectId) {
      this.$router.push({
        name: "jkuserproject",
        params: { projectId: projectId }
      });
    }
  },
  created: function() {
    // this gathers the user id from the previous route and pushes it into this document
    this.getProjects(this.$route.params.userId);
  }
};
</script>

<style>
.designer-header,
.jk-designer-bar {
  background-color: black;
}


.jk-previous-button {
  padding-top: 3em;
  padding-left: 30em;
  height: 35px;
}

.jk-project {
  display: flex;
  flex-direction: row;
  justify-content: center;
}

.jk-projects {
  padding: 10em 2em 0em 2em;

}

.jk-projects p {
  margin: 2px 0 0 0;
  font-size: 10px;
  color: #abafb5;
}

.jk-projects p,
.jk-projects h4 {
  font-family: acumin-pro, sans-serif;
}

.jk-projects h4 {
  font-weight: 700;
}
</style>