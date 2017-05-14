<template>
  <div class="portfolio">
    <overview-component></overview-component>
    <about-component></about-component>
    <projects-component></projects-component>
  </div>
</template>

<script>
import AboutComponent from './About';
import OverviewComponent from './Overview';
import ProjectsComponent from './Projects';

export default {
  name: 'Portfolio',
  components: {
    OverviewComponent,
    ProjectsComponent,
    AboutComponent,
  },
};
</script>
