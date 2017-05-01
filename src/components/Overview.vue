<template>
  <div class="overview text-xs-center">
    <div class="title">
      <h1>Joseph Moran</h1>

      <h2 class="subtitle">
        <span class="image-holder">
          <img class="tech-image" :src="imgUrl" />
        </span>
        Developer
      </h2>
    </div>

    <v-container class="social-network-container">
      <v-row>
        <v-col xs4>
          <a href="https://github.com/KnightVision90">
            <img src="../assets/img/logos/github.png" alt="github">
          </a>
        </v-col>
        <v-col xs4>
          <a href="https://www.linkedin.com/in/joseph-moran-58a30882">
            <img src="../assets/img/logos/linkedin.png" alt="linked in">
          </a>
        </v-col>
        <v-col xs4>
          <a href="https://www.twitter.com/streammythos">
            <img src="../assets/img/logos/twitter.png" alt="twitter">
          </a>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'Overview',
  data() {
    return {
      index: 0,
      logos: [
        'php.gif',
        'javascript.png',
        'laravel.png',
        'nodejs.png',
        'mysql.png',
        'mssql.png',
      ],
      pathToLogos: require.context('../assets/img/logos', false),
    };
  },
  computed: {
    imgUrl() {
      return this.pathToLogos(`./${this.logos[this.index]}`);
    },
  },
  created() {
    setInterval(() => {
      this.index = (this.index + 1) % this.logos.length;
    }, 2000);
  },
};
</script>

<style lang="scss" scoped>
  @import '../../src/assets/css/_colors.scss';

  .overview {
    background: url('../assets/img/main-photo.jpg') fixed;
    background-size: cover;
    height: 100%;
    width: 100%;
    min-height: 100vh;

    .title {
      h1 {
        padding-top: 20vh;
        color: $white;
        -webkit-text-stroke: 2px $dark_blue;
      }
      h2 {
        padding-top: 5vh;
        color: $light_blue;
        -webkit-text-stroke: 2px $dark_blue;
      }
    }

    .subtitle{
      line-height: 100px;
      vertical-align: middle;
      .image-holder {
        display: inline-block;
        width: 100px;
        height: 100px;

        .tech-image {
          max-width: 100%;
          max-height: 100%;
          vertical-align: middle;
        }
      }
    }

    .social-network-container {
      margin-top: 5vh;

      img {
        border-radius: 40px;
        height: 75px;

        &:hover {
          box-shadow: $white 0 0 50px;
        }
      }
    }
  }

</style>
