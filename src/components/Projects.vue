<template>
  <div class="wrapper">
    <div class="projects-tabs">
      <ul class="tabs">
        <li
          v-for="project in projects"
          v-bind:key="project.id"
          @click="clickToactive(project.id)"
        >
          <div :class="{ focus: projects[project.id].active }"> {{ project.name }} </div>
        </li>
      </ul>
    </div>

    <div class="projects-description">
      <div
        class="description"
        v-for="project in activeProject"
        :key="project.id"
      >
        <div class="project-img">
          <a :href="project.githubLink">
            <img
              v-if="project.img"
              :src="require(`@/assets/img/` + project.img)"
              :alt="project.name"
            >
          </a>
        </div>
        <div class="project-info">
          <p> {{ project.description }} </p>
          <p v-if="project.info"> {{ project.info}} </p>
          <div
            class="coding-logo"
            v-if="project.coding"
          >
            <img
              :src="require(`@/assets/img/` + project.coding)"
              :alt="project.coding"
            >
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          id: 0,
          name: "About me",
          description:
            "Hey I'm Gert Vandormael a motivated web developer equipped with knowledge of html, css, javascript, vue.js and php.",
          info: "Click on the projects above to see more info about them.",
          coding: null,
          img: null,
          githubLink: null,
          githubSource: null,
          active: true
        },
        {
          id: 1,
          name: "Idle game",
          description: "Become the world's greatest band by clicking!",
          coding: "vue.png",
          img: "project-idle-game.png",
          githubLink: "https://gertvandormael.github.io/idle-game/",
          githubSource: "https://github.com/gertvandormael/idle-game",
          active: false
        },
        {
          id: 2,
          name: "RPG",
          description:
            "Turn based RPG with a basic character creation. 2 player game where you can battle against each other",
          coding: "javascript.png",
          img: "project-rpg.png",
          githubLink: "https://birthelambrechts.github.io/RPG-challenge",
          githubSource: "https://github.com/gertvandormael/RPG-challenge",
          active: false
        },
        {
          id: 3,
          name: "Piano",
          description: "Playable piano with sounds",
          coding: "javascript.png",
          img: "project-piano.png",
          githubLink: "https://gertvandormael.github.io/piano/piano.html",
          githubSource: "https://github.com/gertvandormael/piano",
          active: false
        },
        {
          id: 4,
          name: "MVC webshop",
          description: "Webshop made with a MVC structure",
          coding: "php.png",
          img: "project-mvc.png",
          githubLink: null,
          githubSource: "https://github.com/gertvandormael/mvc",
          active: false
        }
      ]
    };
  },

  computed: {
    activeProject() {
      return this.projects.filter(function(u) {
        return u.active;
      });
    }
  },

  methods: {
    clickToactive(id) {
      for (let i = 0; i < this.projects.length; i++) {
        this.projects[i].active = false;
        this.projects[id].active = true;
      }
    }
  }
};
</script>

<style scoped>
.tabs {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px 0px 25px 0px;
  height: 100px;
}

li {
  background: -webkit-linear-gradient(#368F8B, #160F29);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #d3c0d2;
  font-size: 1.5rem;
  cursor: pointer;
}

li:hover {
  background: -webkit-linear-gradient(#160F29, #368F8B);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.focus {    
  color: #160F29;
  font-size: 1.5rem;
  font-weight: 700;
}

.projects-description {
  display: flex;
  justify-content: center;
}

/* Large devices (desktops, 992px and up) */
/* @media (min-width: 992px) { */
  .projects-description {
  display: flex;
  justify-content: center;
  height: 550px;
  width: 800px;
  padding: 30px 15px 30px 15px;
  background: #f5f5f5;
  color: #160F29;
  border-radius: 50px;
  border: 1px solid black;
  }
/* } */

.project-info {
  width: 600px;
}

.projects-description img {
  max-width: 600px;
  max-height: 500px;
  margin-bottom: 5px;
}

.projects-description p {
  margin-bottom: 10px;
}

button {
  background: none;
  border: none;
  outline-style: none;
  font-family: "Montserrat", sans-serif;
}


.coding-logo img {
  max-width: 45px;
  max-height: 30px;
}





</style>

