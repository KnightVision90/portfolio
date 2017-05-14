<template>
  <div id="footer" class="text-xs-center">
    <div class="made-by">
      Made With Love By Me
    </div>
    <div class="copywrite">
      &copy;{{ year }}
    </div>
  </div>
</template>

<script>
  export default {
    name: 'footer',
    data() {
      return {
        year: (new Date()).getFullYear(),
      };
    },
  };
</script>

<style lang="scss" scoped>
  @import '../assets/css/_colors';

  #footer {
    padding: 2vh 0;
    background-color: $black;
    font-weight: bold;

    .made-by {
      color: $white;
    }

    .copywrite {
      color: $light_blue;
    }
  }
</style>
