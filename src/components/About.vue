<template>
  <div id="about">
    <h3 class="text-xs-center">What I Do</h3>
    <h4 class="text-xs-center">More than a one trick developer</h4>
    <v-container class="about-container">
      <v-row>
        <v-col xs12 md4 class="text-xs-center summary">
          <v-icon>developer_board</v-icon>
          <h5>Structure</h5>
          <p>
            Whether you need to allow customers to buy products, spread information with a blog, or need a tool to help
            your business workflow, I can structure a system to get it done.
          </p>
        </v-col>

        <v-col class="text-xs-center summary" xs12 md4>
          <v-icon>visibility</v-icon>
          <h5>Identify</h5>
          <p>
            Sometimes a new pair of eyes can help identify opportunities and pinpoint inefficiencies. You could say I
            have an eye for optimization.
          </p>
        </v-col>

        <v-col xs12 md4 class="text-xs-center summary">
          <v-icon>merge_type</v-icon>
          <h5>Integrate</h5>
          <p>
            Sometimes you see an awesome feature you'd like on your site and sometimes you dream it up all on your own.
            Either way, I can help add it to your site.
          </p>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
    export default {
      name: 'about',
    };
</script>

<style lang="scss" scoped>
  @import '../assets/css/_colors.scss';

  #about {
    padding: 5vh 0 5vh;
    background-color: $white;

    h3 {
      padding: 5vh 0 0;
      color: $dark_blue;
      font-weight: bold;
    }

    h4 {
      color: $blue;
      font-weight: lighter;
    }

    .about-container {

      .summary {
        padding: 5vh 0;

        .material-icons {
          background-color: $red;
          border-radius: 50%;
          padding: 10px;
          color: $white;
          font-size: 6em;
        }

        h5 {
          margin: 2vh 0 0;
          color: $dark_blue;
          font-weight: bold;
        }

        p {
          padding: 2vh 0 0;
          color: $blue;
        }
      }
    }
  }
</style>
