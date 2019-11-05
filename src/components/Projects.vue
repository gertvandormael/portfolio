<template>
  <div class="wrapper">
    <div class="projects-tabs">
      <ul class="tabs">
        <li
          v-for="project in projects"
          v-bind:key="project.id"
          @click="ClickToActivate(project.id)"
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
            class="coding-info"
            v-if="project.coding"
          >
            <img
              :src="require(`@/assets/img/` + project.coding)"
              :alt="project.coding"
              target="_blank"
            >
            <ul class="links">
              <li><a
                  :href="project.githubLink"
                  target="_blank"
                >Project link</a></li>
              <li><a
                  :href="project.githubSource"
                  target="_blank"
                >Source code</a></li>
            </ul>
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
            "Hey I'm Gert Vandormael a motivated web developer equipped with knowledge of HTML, CSS, JavaScript, Vue.js and PHP.",
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
          description:
            "Become the world's greatest band by clicking! Interactive page where clicking alters the content.",
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
          description:
            "In my free time I play piano so I recreated a playable piano with JavaScript",
          coding: "javascript.png",
          img: "project-piano.png",
          githubLink: "https://gertvandormael.github.io/piano/piano.html",
          githubSource: "https://github.com/gertvandormael/piano",
          active: false
        },
        {
          id: 4,
          name: "MVC webshop",
          description:
            "Webshop made with a MVC structure as an introduction to PHP frameworks like Laravel and Symfony",
          coding: "php.png",
          img: "project-mvc.png",
          githubLink: "https://github.com/gertvandormael/mvc",
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
    ClickToActivate(id) {
      for (let i = 0; i < this.projects.length; i++) {
        this.projects[i].active = false;
        this.projects[id].active = true;
      }
    }
  }
};
</script>

<style scoped>
/* Tabs */
.tabs {
  text-align: center;
}

.tabs li {
  background: -webkit-linear-gradient(#368F8B, #160F29);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  color: #d3c0d2;
  font-size: 1.2rem;
  padding: 5px 0px 5px 0px;
  cursor: pointer;
}

.tabs li:hover {
  background: -webkit-linear-gradient(#160F29, #368F8B);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

.focus {    
  color: #160F29;
  font-size: 1.2rem;
  font-weight: 700;
}

/* Projects section */
.projects-description {
  display: flex;
  justify-content: center;
}

.projects-description {
  display: flex;
  justify-content: center;
  background: #f5f5f5;
  color: #160F29;
  padding: 30px 15px 30px 15px;
  border-radius: 50px;
  border: 1px solid black;
  min-width: 150px;
  max-width: 800px;
}
 
.project-img img {
  max-width: 300px;
  max-height: 200px;
  margin-bottom: 5px;
}

.projects-description p {
  margin-bottom: 10px;
  width: 300px
}

a {
  text-decoration: none;
  color: #368F8B;
}

a:hover {
  color: #160F29;
}

.coding-info {
  display: flex;
  align-content: center;
}

.coding-info img {
  max-width: 60px;
  max-height: 36px;
  margin-right: 8px;
}


/* // Medium devices (tablets, 768px and up) */
@media (min-width: 768px) {
  .tabs {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 100px;
  }

    .tabs li {
    font-size: 1.5rem;
  }

  .focus {    
    font-size: 1.5rem;
    border-bottom: #160F29 2px solid;
  }

  .projects-description p {
    width: 600px;
  }

  .project-img img {
    max-width: 600px;
    max-height: 500px;
  }
}

/* Large devices (desktops, 992px and up) */
 @media (min-width: 992px) { 
  .tabs li {
    font-size: 1.5rem;
  }

  .focus {    
    font-size: 1.5rem;
    border-bottom: #160F29 2px solid;
  }

  .projects-description {
    height: 550px;
    width: 800px;
  }

  .project-info {
    width: 600px;
  }
}
</style>

