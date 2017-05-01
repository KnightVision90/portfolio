<template>
  <div class="portfolio">
    <overview-component></overview-component>
  </div>
</template>

<script>
import OverviewComponent from './Overview';

export default {
  name: 'Portfolio',
  components: {
    OverviewComponent,
  },
};
</script>
