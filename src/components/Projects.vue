<template>
  <div id="past-works">
    <h3 class="text-xs-center">Projects</h3>
    <hr>
    <v-container fluid="true">
      <v-row>
        <v-col v-for="(project, index) in projects" :key="index" xs12 lg4 class="project-container">
          <div class="project">
            <a :href="project.url">
              <h4 class="text-xs-center">{{ project.name }}</h4>
              <img :src="getProjectImage(project.imageName)" :alt="project.name" class="screenshot-web">
            </a>

            <hr>

            <div class="project-description">
              <strong>Description:</strong> {{ project.description }}
            </div>

            <hr>

            <div class="project-tech">
              <strong>Tech Used:</strong> {{ project.technologies.join(', ') }}
            </div>
          </div>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
  export default {
    name: 'Projects',
    data() {
      return {
        pathToProjects: require.context('../assets/img/sites', false),
        projects: [
          {
            name: 'CFDV',
            imageName: 'cfdv',
            url: 'http://www.cfdv.org',
            description: 'CFDV was a freelance project done for a scientific non-profit. It features a custom build CMS to allow the administrators to create events, job postings, awards, and allows users to register for events, buy membership, and inquire about sponsoring events.',
            technologies: ['Laravel', 'PHP', 'Bootstrap', 'PayPal API', 'MySql', 'Apache'],
          },
          {
            name: 'The Restaurant Store',
            imageName: 'trs',
            url: 'https://www.therestaurantstore.com',
            description: 'As a full-time employee of Clark Associates, I worked to rewrite the entire e-commerce website as well as create a Payment API that is to be used across multiple company sites.',
            technologies: ['Laravel', 'PHP', 'JavaScript', 'jQuery', 'PayPal API', 'Authorize.Net', 'MsSql', 'Swagger', 'Gulp'],
          },
          {
            name: 'My /r/ Stream',
            imageName: 'myrstream',
            url: 'https://myrstream.herokuapp.com',
            description: 'A newly created open-source personal project to allow a user to frequently update the user to Reddit content, allowing the user to remain up to date across multiple channels.',
            technologies: ['Vue', 'Webpack', 'Node.js', 'Reddit API', 'Heroku'],
          },
        ],
      };
    },
    methods: {
      getProjectImage(name) {
        return this.pathToProjects(`./${name.toLowerCase()}.jpg`);
      },
    },
  };
</script>

<style lang="scss" scoped>
  @import '../assets/css/_colors.scss';

  #past-works {
    background-color: $dark_blue;
    padding: 0 10px;

    h3 {
      padding: 5vh 0 2vh;
      color: $red;
    }

    & > hr {
      border: 1px solid $white;
      background-color: $white;
      margin: 2vh auto 5vh;
      width: 70%;
    }

    .project-container {
      padding: 10px;

      .project {
        background-color: $white;
        padding: 5px;
        height: 100%;
        box-shadow: 0 0 10px $black;

        a {
          text-decoration: none;
          display: block;

          &:hover {
            h4 {
              color: $red;
            }
            .screenshot-web {
              border-color: $red;
            }
          }

          h4 {
            color: $blue;
          }
          .screenshot-web {
            max-width: 98%;
            display: block;
            border: 1px solid $blue;
          }
        }

        hr {
          background-color: $red;
          border: 1px solid $red;
          margin: 5px 0;
        }

        .project-description {
          color: $black;
        }
      }
    }
  }
</style>
