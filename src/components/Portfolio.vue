<template>
  <div class="portfolio">
    <overview-component></overview-component>
    <projects-component></projects-component>
  </div>
</template>

<script>
import OverviewComponent from './Overview';
import ProjectsComponent from './Projects';

export default {
  name: 'Portfolio',
  components: {
    OverviewComponent,
    ProjectsComponent,
  },
};
</script>
