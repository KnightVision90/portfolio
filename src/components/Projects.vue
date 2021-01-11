<template>
  <div id="past-works">
    <h3 class="text-xs-center">Projects</h3>
    <h4 class="text-xs-center">Turning ideas into reality</h4>
    <v-container class="project-row">
      <v-row>
        <v-col v-for="(project, index) in projects" :key="index" xs12 lg6 class="project-container">
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
            name: 'The Restaurant Store',
            imageName: 'trs',
            url: 'https://www.therestaurantstore.com',
            description: 'As a full-time employee of Clark Associates, I worked to rewrite the entire e-commerce website as well as create a Payment API that is to be used across multiple company sites.',
            technologies: ['Laravel', 'PHP', 'JavaScript', '.Net Core', 'C#', 'Vue', 'T-Sql', 'GraphQL', 'PayPal API', 'Authorize.Net', 'Swagger'],
          },
          {
            name: 'CFDV',
            imageName: 'cfdv',
            url: 'http://www.cfdv.org',
            description: 'CFDV was a freelance project done for a scientific non-profit organization. It features a custom built CMS to allow the administrators to create events, job postings, and awards.  In addition, it allows users to register for events, buy membership, and inquire about sponsoring events.',
            technologies: ['Laravel', 'PHP', 'Bootstrap', 'PayPal API', 'MySql', 'Apache'],
          },
          {
            name: 'Estate Liquidation Service',
            imageName: 'els',
            url: 'http://www.estateliquidationservice.co',
            description: 'Estate Liquidation Service was a freelance project done for a close family member\'s business. It features an admin approval registration system, functionality to let users request items from estates and commit to picking them up for a specified price, and an admin side to perform, manage, and track sales.',
            technologies: ['Laravel', 'PHP', 'Vue', 'MySql', 'Apache', 'Websockets'],
          },
          {
            name: 'My /r/ Stream',
            imageName: 'myrstream',
            url: 'https://myrstream.herokuapp.com',
            description: 'An open-source personal project to frequently update a user with recent Reddit content, allowing the user to remain up to date across multiple channels.',
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
    padding: 5vh 0 5vh;

    h3 {
      padding: 5vh 0 0;
      color: $red;
      font-weight: bold;
    }

    h4 {
      color: $white;
      font-weight: lighter;
    }

    .project-row {
      .project-container {
        padding-top: 5vh;
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

          .project-description {
            color: $black;
          }
        }
      }
    }
  }
</style>
